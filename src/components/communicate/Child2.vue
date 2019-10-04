<template>
    <div>
        <h2>Child2</h2>
        <h3>{{msg}}</h3>
        <grand-child1>
        </grand-child1>
    </div>
</template>
<script>
import GrandChild1 from '@/components/communicate/GrandChild1'
export default {
    name:'Child2',

    props:['title'],
    data(){
        return {
            msg:""
        }
    },
    components:{
        GrandChild1,
    },
    methods:{
        toParent(){
            this.$emit('getmsg','爸爸,我知道错了')
        }
    },
    mounted(){
    this.$bus.$on("event-bus", msg => {
      this.msg = "接收event-bus消息child2:" + msg;
    });
        this.$on("dispatch",msg=>{
            this.msg = '接收dispatch消息:'+ msg
        })
    }
    
}
</script>

