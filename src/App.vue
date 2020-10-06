
<template>
<SubmissionComponent
 v-bind:user="user"
 v-bind:sortedinfo="sortedInfo"
></SubmissionComponent>
</template>
<script>
import users from "../users";
import SubmissionComponent from "./components/submission-component.vue";
export default {
  el: '#app',
  data: () => {
    return {user: users}
  },
  computed: {
    sortedInfo(){
      return this.user.sort((a,b) => b.votes - a.votes )
    }
  },
  // methods:{
  //   upvote(voteId){
  //     const data = this.user.find(item => item.id === voteId);
  //     data.votes++;
  //   }
  // },
  components:{
    SubmissionComponent
  }
}

</script>