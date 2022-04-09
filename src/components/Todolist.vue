<template>
	<div>
    <main class="todo">
        <div class="container">
            <h1>To - Do List</h1>
			<TodoInput @addTodo = "addTodo"> </TodoInput>
            <ul class="todo_list">
                <li class="todo_list_tit"><p>할 일</p></li>
                <li class="del_btn" v-for="(item,index) in todolist" :key="index">
                    <p>
                        <input type="checkbox" name="check1" value="">{{item.todo}}
                    </p>
                    <ul class="todo_list_btn">
                        <li><button>수 정</button></li>
                        <li><button @click="subTodo">삭 제</button></li>
                    </ul>
                </li>
            </ul>

        </div>
    </main>	
	</div>
</template>

<script>
import TodoInput from './TodoInput.vue'
export default {
  name: 'Todolist',
  components: {
	  TodoInput
  },
  data: function() {
	return {
		todolist:[
			{todo:"Vue.js 공부하기"},
			{todo:"네트워크보안 서브노트 작성하기"},
			{todo:"실기 강의 듣기"},
			{todo:"과제 제출하기"},
			{todo:"책상 정리하기"},
		]
	}
  },
  methods: {
	  addTodo(val){
		  this.todolist.push({todo:val});
		  this.addText = "";
	  },
	  subTodo(idx){
		  this.todolist.splice(idx, 1);
	  }
  }
}
</script>

