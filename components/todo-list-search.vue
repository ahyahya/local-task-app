<template>
  <div class="todo-list-search">
    <div class="todo-list-search-left">
      <div>{{name}}</div>
    </div>
    <div class="todo-list-search-right">
      <div>登録日: {{parsedCreatedAt}}</div>
    </div>
  </div>
</template>

<style scoped>
.todo-list-search {
  cursor: pointer;
  color: white;
  padding: 20px 40px;
  border-top: 1px solid rgba(255,255,255,0.6);
  background: rgba(254,245,228,0.02);
  display: flex;
  justify-content: flex-start;
}
.todo-list-search-left {
  width: 400px;
  padding-right: 50px;
  display: flex;
  align-items: center;
  font-size: 24px;
  justify-content: flex-end;
  border-right: 1px solid rgba(160,160,160,0.3);
}
.todo-list-search-right {
  display: flex;
  align-items: center;
  padding-left: 50px;
  font-size: 14px;
}
</style>

<script>
import dateFormat from '~assets/js/date-format';

export default {
  computed: {
    parsedCreatedAt() {
      return dateFormat(this.createdAt);
    }
  },
  props: {
    name: {
      type: String,
      required: true
    },
    createdAt: {
      type: Date,
      required: true
    }
  }
};

</script>
