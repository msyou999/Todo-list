<template>
  <div class="hello">
	<a :href=url>Link to Naver!</a>
	<h2 :align='align'>오른쪽 정렬하기</h2>
	<h2 :style="{ backgroundColor : bgColor }">노란색</h2>
	<h1>이름은 {{ object.name }}이고, 나이는 {{ object.age }}살 입니다.</h1>
	<h3 :class="flag? 'gray':'' ">Class CSS</h3>
	  
	<input type="text" v-model="msg"/>
	<h3 :class="msg">{{ msg }}</h3>
	  
	<input type="radio" v-model="radio" value="skyblue">skyblue
	<input type="radio" v-model="radio" value="gray">gray
	<input type="radio" v-model="radio" value="pink">pink
	<p :class="radio">Radio Button</p>
	  
	<input type="checkbox" v-model="checkbox" value="skyblue">skyblue
	<input type="checkbox" v-model="checkbox" value="gray">gray
	<input type="checkbox" v-model="checkbox" value="pink">pink
	  
	<h3 @click="hi">Hello</h3>
	<h3 @click="bye">Bye</h3>
	  
	<ul v-for="item in items">
		<!-- <li>{{ item.name + "의 가격은 " item.price + "원 입니다." }}</li> -->
	</ul>
  </div>
</template>

<script>
var code = { name:'MS', age: 24 };
export default {
  name: 'HelloWorld',
	data: function() {
		return {
		  	msg: '',
			array: ['자몽', '오렌지', '딸기'],
			object: code,
			url: 'https://www.naver.com',
			align: 'right',
			bgColor: 'yellow',
			flag: true,
			radio: '',
			items: [
				{ name:'햄버거', price:'7000' },
				{ name:'떡볶이', price:'14000' },
				{ name:'치킨', price:'20000' },
			],
		}
	},
	computed: {
		flag2: function() {
			if(this.msg) return 'gray';
		}
	},
	methods: {
		hi: function() {
			alert('안녕하세요');
		},
		bye: function() {
			alert('안녕히 가세요');
		},
	},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

h3 {
  margin: 40px 0 0;
}
a {
  color: #42b983;
}
.gray {
	background-Color: gray;
}
.skyblue {
	background-Color: skyblue;
}
.pink {
	background-Color: pink;
}
</style>
