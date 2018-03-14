<template>
    <div class="register">
        <el-row type="flex" justify="space-between" align="middle" class="el-row">
            <el-col :span="24">
               <el-input v-model="name" placeholder="请输入姓名"></el-input>
            </el-col>
        </el-row>
        <el-row type="flex" justify="center" align="middle" class="el-row">
            <el-col :span="24">
                <el-date-picker
                style="width:100%"
                v-model="date"
                type="date"
                placeholder="请选择您的出生年月">
                </el-date-picker>
            </el-col>
        </el-row>
        <div class="sex">
            <span>请选择您的性别:</span><input type='radio' id="man" v-model="sex" name="sex" value="男"><label for="man">男</label><input type="radio" name="sex" id="woman" v-model="sex" value="女"><label for="woman">女</label>
        </div>
        <el-row type="flex" justify="space-between" align="middle" class="el-row">
            <el-col :span="24">
               <el-input v-model="mobile" placeholder="请输入您的手机号"></el-input>
            </el-col>
        </el-row>
        <el-row type="flex" justify="space-between" align="middle" class="el-row">
            <el-col :span="17">
               <el-input v-model="num" placeholder="请输入验证码"></el-input>
            </el-col>
            <el-col :span="6">
                <el-button class="btn-code" style="width: 100%">获取验证码</el-button>
            </el-col>
        </el-row>
        <el-row type="flex" justify="space-between" align="middle" class="el-row">
            <el-col :span="24">
               <el-input v-model="pass" type="password" placeholder="请设置密码"></el-input>
            </el-col>
        </el-row>
        <el-row type="flex" justify="space-between" align="middle" class="el-row">
            <el-col :span="24">
               <el-input v-model="code" placeholder="请填写邀请码(可选填)"></el-input>
            </el-col>
        </el-row>
        <div class="my-checkbox">
            <input type="checkbox" id="one" v-model="one"><label for="one">同意掌心猫注册《服务协议》</label>
        </div>
        <div class="my-checkbox">
            <input type="checkbox" id="two" v-model="two"><label for="two">本人同意免费领取平安交通意外伤害保险《投标须知》,<br>同意中国平安后续致电联系确认保险产品相关事宜。
            </label>
        </div>
        <el-button class="btn" style="width:100%">注册</el-button>
    </div>
</template>
<script>
export default {
  data(){
      return {
          name: '',
          date: '',
          pass: '',
          sex: '男',
          mobile: '',
          num: '',
          code: '',
          one: true,
          two: true
      }
  }
}
</script>
<style lang="stylus" scoped>
    rem(px){
        return px/75 rem
    }
    .register
        width: 100%
        height: 100%
        background url('../assets/bj.png')
        background-size 100%
        background-repeat no-repeat
        padding: rem(350) rem(20) 0
        box-sizing border-box
        background-color: #cf1e0c
    .el-row
        margin: 10px 0
    .my-sex
        font-size rem(30)
        color: #ffffff
        line-height rem(30)
        display block
        padding 0 rem(20)
    .my-checkbox
        display flex
        align-items center
        color #f3a307
        font-size rem(26)
        margin rem(10) 0
        input
            display none
            &:checked+label:after
                background-image url('../assets/yes.png') 
        label
            display block
            margin-left rem(10)
            position relative
            padding-left rem(45)
            &::after
                content: '';
                display block 
                background #ffffff
                background-repeat no-repeat
                background-size 80% 80%
                background-position center center
                border-radius 2px
                position: absolute
                width: rem(35);
                height: rem(35);
                left 0
                top 0
                bottom 0 
                margin auto 0
                vertical-align: middle;
    .sex
        color: #ffffff
        font-size rem(30)
        display flex
        justify-content center
        align-items center
        span
            display block
            padding 0 rem(30)
        input
            display none
            &:checked+label:after
                background-color #fbbf04
        label
            display block
            width rem(100)
            position relative
            padding-left rem(60)
            &::after
                content: '';
                display block 
                background-image url('../assets/man.png')
                background-repeat no-repeat
                background-size 80% 80%
                background-position center center
                position: absolute
                width: rem(50);
                height: rem(50);
                border-radius 50%
                left 0
                top 0
                bottom 0 
                margin auto 0
                vertical-align: middle;
            &:last-child::after
                background-image url('../assets/woman.png')
    .btn-code
        color: #df491b
        background: #ffcb0c
        padding: 12px rem(10) 
    .btn
        color: #ffffff
        background: #fbbf04
        margin rem(10) 0
</style>


