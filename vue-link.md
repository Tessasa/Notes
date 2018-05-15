###跳转外部链接
```
window.location.href = url
```


###跳转动态链接（后台数据）
```
<template>
    <div class="addLessons" @click="addLessonFun('param')"></div>
    <div>
</template>

<script>
      export default {\
           methods: {
            addLessonFun(event) {
                this.$router.push(this.addLessonLink);
                this.$router.push({name: '/order/page1',params:{ id:'1'}});
                this.$router.push({path: '/order/page1',query:{ id:'2'}});
            }
        }
     }
</script>
```

###内部静态链接
```
    <router-link to="/share" ">分享</router-link>
```
