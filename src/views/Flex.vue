<template>
<div class="container">
		<div v-for="(div,index) in divs" class="inner">
			<div v-for="left,index2 in div.inner">
				<div class="leftcircle">
					   <div class="circle">
				            <!--左半边圆-->
				            <div class="circle_left">
				                <div class="clip_left">
				     			 </div>
				            </div>
				            <!--右半边圆-->
				            <div class="circle_right">
				                <div class="clip_right"></div>
				            </div>

				            <div class="mask">

				                <span class="value">{{left.value}}</span><span class="value" id="percent">%</span>
				                <span class="name">{{left.name}}</span>
				            </div>
				        </div>
				</div>
				<div class="rightmsg"><li  v-for="list in left.message" style="color:#60fcc0;"><span>{{list.msg}}</span></li>	</div>		
			</div>
		</div>
	</div>
</template>

<script>
export default{
		
			data(){
                return {
				"divs":[
					{	
						inner:
						[
							{
								value:20,
								name:"烟感",
								message:[
								{msg:"封包流量：132"},
								{msg:"URL1：https://mall.googal.com/mail/u/1/#inbox"},
								
								]
							},
							
						]
					},
					{	
						inner:
						[
							{
								value:70,
								name:"烟感",
								message:[
								{msg:"封包流量：132"},
								{msg:"URL1：https://mall.googal.com/mail/u/1/#inbox"},
								{msg:"URL2：https://mall.googal.com/mail/u/1/#inbox"},
								]
							},
							
						]
					},
					{	
						inner:
						[
							{
								value:50,
								name:"烟感",
								message:[
								{msg:"封包流量：132"},
								{msg:"URL1：https://mall.googal.com/mail/u/1/#inbox"},
								{msg:"URL2：https://mall.googal.com/mail/u/1/#inbox"},
								]
							},
							
						]
					},
					{	
						inner:
						[
							{
								value:40,
								name:"烟感",
								message:[
								{msg:"封包流量：132"},
								{msg:"URL1：https://mall.googal.com/mail/u/1/#inbox"},
								
								]
							},
							
						]
					}
				]
            }
		}
	}
</script>


<style>

.container{
	display: flex;
	width: 100%;
	height:500px;
	flex-wrap: wrap;
	justify-content: space-around;
	align-items: center;
	background: #323232;
}
.inner{
	width: 45%;
	height:45%;
	background: #2b2b2b;
	position: relative;
}
.leftcircle{
	width:12.5em;
	height: 11.25em;
	display: inline-block;
	margin-top: 1.3em;
	margin-left: 5%;
	border-right: solid 3px #000;
}
.circle {
    width: 11.25em;
    height:11.25em;
    position: relative;
    border-radius: 50%;    
    display: inline-block;
}
         
.clip_left,.clip_right{
	width: 11.25em;
	height: 11.25em;
	position: absolute;
	top: 0px;left: 0px;
}
.circle_left, .circle_right{
    width:11.25em;
    height: 11.25em;
    position: absolute;
    border-radius: 50%;
    top: 0px;left: 0px;
   
}
/*出于展示用的改变背景色*/
.circle_left{
    background:#60fcc0;
}
.circle_right{
    background:#1d4860;
}
.circle_right,.clip_right {
    clip:rect(0,auto,auto,6.25em);
}
.circle_left , .clip_left{
    clip:rect(0,6,25em,auto,0);
}
.mask {
   width: 10em;
    height: 10em;
    border-radius: 50%;
    left: 0.625em;
    top:  0.625em;
    background: #2b2b2b;
    position: absolute;
    color:#fff; 
    text-align: center;
}
.mask>.name{
	display: block;
	font-size: 1.5em;
	background: #1b1b1b;
	width: 50%;
	height: 1.6em;
	border-radius: 35%;
	line-height: 1.6em;
	font-family: Helvetica;
	color: #f1f1f1;
	margin: 0 auto;
	margin-top: -1em;
}
#percent{
	font-size: 1.5em;
}
.mask>.value{
	font-size: 3em;
	color: #3acfb8;
	font-family: sans-serif; 
	line-height: 2.5em;
}
.rightmsg{
	display: inline-block;
	width:50%;
	height: 180px;
	position:absolute;
	font-size: 1rem;
	text-align: left;
	top: 1.5em;
	margin-left: 2em;
}
.rightmsg li{
	height: 4em;
}
.rightmsg span{
	color: #cecece;
}

@media only screen and (max-width:800px){
.container{	
	width: 100%;
	height:auto;
	flex-direction: column;	
	margin-top: 1rem;
}
.inner{	
	width: 95%;
	height:100%;
	padding: 2rem 0;
	margin-top: 2rem;
}
.leftcircle{
	width: 45%;
	height:auto;
	margin-top:0rem;
}
.circle{
	position: relative;
	left: 3em;
}
.rightmsg{
	width:40%;
	height: auto;
}
}
@media only screen and (max-width:480px){
.inner{
	width: 90%;
	height:auto;
	display: flex;	
	flex-direction:column;
}
.leftcircle{
	width:100%;
	height: auto;
	border: 0;
	display: block;
	margin-left: 0em;
  display: flex;
	justify-content: center;
}
.circle{
	left: 0em;
}
.rightmsg{
	position: static;
	width: 100%;
	height: auto;
	text-align: left;
	margin-left: 0em;
}
.rightmsg li{
	width: 70%;
	height: auto;
	line-height: 2em;
	margin: 0 auto;
}
}
</style>