<template>
  <div class="wrapper">
    <img src="http://www.dell-lee.com/imgs/vue3/user.png" alt="" class="wrapper__img">
    <div class="wrapper__input">
      <input
        type="text"
        class="wrapper__input__content"
        placeholder="请输入用户名"
        v-model="data.username"
      >
    </div>
    <div class="wrapper__input">
      <input type="password" class="wrapper__input__content" placeholder="请输入密码" v-model="data.password">
    </div>
    <div class="wrapper__login-button" @click="handleLogin">登录</div>
    <div class="wrapper__login-link" @click="handleRegisterClick">立即注册</div>
    <Toast v-if="data.showToast" :message="data.toastMessage"/>
  </div>
</template>

<script>
import { useRouter } from 'vue-router'
import axios from 'axios'
import { reactive } from 'vue'
import { post } from '@/utils/request'
import Toast from '@/components/Toast'

axios.defaults.headers.post['Content-Type'] = 'application/json'

export default {
  name: 'Login',
  components: { Toast },
  setup () {
    const router = useRouter()
    const data = reactive({
      username: '',
      password: '',
      showToast: true,
      toastMessage: ''
    })
    const handleLogin = async () => {
      const result = await post('/api/user/login', {
        username: data.username,
        password: data.password
      })
      console.log(result)
      if (result?.errno !== 0) {
        data.showToast = false
        // localStorage.isLogin = true
        // router.push({ name: 'Home' })
      } else {
        data.showToast = true
        data.toastMessage = '登录失败'
        setTimeout(() => {
          data.showToast = false
          data.toastMessage = ''
        }, 2000)
      }
      //   .then(res => {
      //   alert('成功')
      //   localStorage.isLogin = true
      //   router.push({ name: 'Home' })
      // }).catch(() => {
      //   alert('失败')
      // })
    }

    const handleRegisterClick = () => {
      router.push({ name: 'Register' })
    }
    return {
      handleLogin,
      handleRegisterClick,
      data
    }
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  transform: translateY(-50%);

  &__login-link {
    font-size: .14rem;
    color: rgba(0, 0, 0, .5);
    text-align: center;
  }

  &__login-button {
    background: #0091ff;
    box-shadow: 0 .04rem .08rem 0 rgba(0, 145, 255, .32);
    border-radius: 4px;
    color: white;
    margin: .32rem .4rem .16rem .4rem;
    text-align: center;
    line-height: .48rem;
    font-size: .16rem;
  }

  &__img {
    display: block;
    width: .66rem;
    height: .66rem;
    margin: 0 auto .4rem auto;
  }

  &__input {
    margin: 0 .4rem .16rem .4rem;
    height: .48rem;
    background: #f9f9f9;
    border: 1px solid rgba(0, 0, 0, .1);
    border-radius: 6px;
    box-sizing: border-box;
    padding: 0 .16rem;

    &__content {
      width: 100%;
      border: none;
      outline: none;
      line-height: .48rem;
      background: none;
      font-size: .16rem;

      &::placeholder {
        color: rgba(0, 0, 0, .5);
      }
    }
  }
}

</style>
