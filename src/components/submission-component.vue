<template>
      <div class="container fluid">
      <div class="row border"
       v-bind:class="{'border-danger': user.votes >= 20}"
       v-for="user in sortedinfo" v-bind:key="user.id" style="margin:10px">
<div class="col-md-3">
  <img 
   v-bind:src="user.thumbnailUrl"
  />
</div>
<div class="col-md-9 text-left">
<a v-bind:href="user.url">
  <span> 
    {{user.title}}
  </span>
  </a><span>#{{user.id}}</span>
  <span class="pull-right">
  <i class="fa fa-chevron-circle-up f-2x" aria-hidden="true"
  v-on:click="upvote(user.id)"
  ></i> {{user.votes}}
  </span>
  <span>
    {{user.username}}
  </span>
</div>
</div>
    </div>
</template>

<script>
export default {
    name: 'SubmissionComponent',
      methods:{
    upvote(voteId){
      const data = this.user.find(item => item.id === voteId);
      data.votes++;
    }
  },
    props:['user','sortedinfo']
}
</script>
