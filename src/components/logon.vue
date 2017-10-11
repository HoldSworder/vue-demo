<template>
  <div>
      <div class="left">
          <h3>注册新账号</h3>
          <div class="message">
              <div class="name">
								 <h4>名字</h4>
                <input type="text" class="input-text" placeholder="真实姓名或常用昵称">
              </div>
							<div class="way">
								<input type="radio" id="phone" value="phone" v-model="way">
								<label for="phone" >用手机号注册</label>
								<input type="radio" id="mail" value="mail" v-model="way">
								<label for="mail" >用邮箱注册</label>
								<input type="text" class="input-text" placeholder="仅支持大陆手机号" v-if="way === 'phone'">
								<input type="text" class="input-text" placeholder="短信验证码" v-if="way === 'phone'">
								<input type="text" class="input-text" placeholder="hello@qzr1996.com" v-if="way === 'mail'">
							</div>
							<div class="password">
								<h4>密码</h4>
								<input type="text" class="input-text" placeholder="不少于6位">
							</div>
							<span>同意并接受《服务条款》</span>
							<button @click="logon">注册</button>
          </div>
      </div>
  </div>
</template>

<script>
export default {
	data() {
		return {
			way: 'phone'
		}
	},
	methods: {
		logon() {
			this.$emit('logon')
		} 
	}
}
</script>

<style scoped>
h3{
	font-size: 18px;
	color: #777;
	margin-top: 0;
	font-weight: normal;
}
h4{
	display: block;
	max-width: 100%;
	margin-bottom: 5px;
	font-weight: bold;
}
.input-text{
	display: block;
	margin: 5px 0;
	width: 100%;
	height: 20px;
	padding: 6px 12px;
	font-size: 14px;
	line-height: 1.42858;
	color: #555;
	background-color: #fff;
	background-image: none;
	border: 1px solid #ccc;
	border-radius: 4px;
}
#phone,#mail{
	display: inline;
}
div{
	margin: 10px;
}
button{
	background-color: #009a61;
	border-color: #008151;
	color: #fff;
	display: inline-block;
	margin-bottom: 0;
	font-weight: normal;
	text-align: center;
	vertical-align: middle;
	cursor: pointer;
	background-image: none;
	border: 1px solid transparent;
	white-space: nowrap;
	padding: 6px 12px;
	font-size: 14px;
	line-height: 1.42858;
	border-radius: 4px;
	-webkit-user-select: none;
	-moz-user-select: none;
	-ms-user-select: none;
	user-select: none;
}
</style>


