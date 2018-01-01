<template>
	<div class="wrap">
		<header>
			<div class="container">
				<a class="logo" @click="queryString(32212345)"></a>
				<a @click="queryNum('ababasasqc')">Length</a>
				<a @click="querySite([3, 1, 3, 6, 2, 3, 4, 5])">Site</a>
			</div>
		</header>
		<nav>
		</nav>
		<div class="content"></div>
		<footer></footer>
	</div>
</template>

<script>
 export default {
  methods: {
	querySite(val) {
	  let sortArr = val.sort(function(a, b){
		return a > b;
	  })
	  console.log(sortArr);
	},
	queryString(val) {	
	  let strArr = ['一','二','三','四','五','六','七','八','九','十'];
	  let str = '';
	  let valSplit = val.toString().split("").reverse();
	  for(let i = valSplit.length-1;i>=0;i--) {
	  	switch(valSplit[i]) {
	  	  case "1": str += strR(val,"一", i);break;
	  	  case "2": str += strR(val,"二", i);break;
	  	  case "3": str += strR(val,"三", i);break;
	  	  case "4": str += strR(val,"四", i);break;
	  	  case "5": str += strR(val,"五", i);break;
	  	  case "6": str += strR(val,"六", i);break;
	  	  case "7": str += strR(val,"七", i);break;
	  	  case "8": str += strR(val,"八", i);break;	  	  	  	  	  	  
		  case "9": str += strR(val,"九", i);break;
		  default: '0';break;	  	
	  	}

	  	function strR(str, val, index) {
	  		let siteArr = ['亿','千万','百万','十万','万','千','百','十',''].reverse();
	  		return val + siteArr[index];
	  	}
	  }
	  console.log(str); 
	 },
	 queryNum(val) {
		let obj = {}
		for(let i = 0;i < val.length;i++) {
		  let v = val.charAt(i);
		  if(obj[v] && obj[v].value == v) {
			obj[v].count = ++ obj[v].count;
			}else{
				obj[v] = {};
				obj[v].count = 1;	
				obj[v].value = v;
			}
		}
		console.log(obj)
   }
  }
 }

</script>

<style scoped>
	.wrap{
		width:100%;
		height:100%;
		display:flex;
		display:-webkit-flex;
		display:-moz-flex;
		display:-o-flex;
		flex-direction:column;
	}
	header{
		width:100%;
		height:1.2rem;
		position:relative;
	}
	.logo{
		float:left;
		margin-top:0.2rem;	
		width:100px;
		height:40px;
		background:url("../assets/boc2013_logo.png");
		background-size:100% 100%;
	}
	nav{
		width:100%;
		height:1.5rem;
		background:red;
	}
	.content{
		flex:1;
	}
	footer{
		width:100%;
		height:2rem;
		background:#f2f2f2;
	}
</style>