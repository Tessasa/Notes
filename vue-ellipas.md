```
export default {
  name: "live-broadcast",
  data(){
        return  {
            maxLength: '57',
            text : '在这里，有一座历史千年的古刹，它经历过佛教鼎盛的时代，也经历了破败，在1999年因腿部疾病的释广静法师在中学毕业后,在这里，有一座历史千年的古刹，它经历过佛教鼎盛的时代，也经历了破败，在1999年因腿部疾病的释广静法师在中学毕业后'
        }
  },
  mounted (){
        console.log('text length:',this.text.length);
        //  控制文本溢出省略
        if(this.text.length > this.maxLength){
            this.text = this.text.slice(0,this.maxLength) + '...';
        }
  }
};
  ```

###效果
  ```
  在这里，有一座历史千年的古刹，它经历过佛教鼎盛的时代，
  也经历了破败，在1999年因腿部疾病的释广静法师在中学毕
  业后...
  ```