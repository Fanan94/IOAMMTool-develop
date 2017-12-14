<template>
	<div id="addUser">
		<!-- settings changer -->
        <div class="skins-nav">
            <a href="#" class="skin first_nav selected">
                <span class="icon"></span><span class="text">Default</span>
            </a>
            <a href="#" class="skin second_nav" data-file="css/skins/dark.css">
                <span class="icon"></span><span class="text">Dark skin</span>
            </a>
        </div>


		<div class="container-fluid">
            <div id="pad-wrapper" class="new-user">
                <div class="row-fluid header">
                    <h3>创建一个新用户</h3>
                </div>

                <div class="row-fluid form-wrapper">
                    <!-- left column -->
                    <div class="span10 with-sidebar">
                        <div class="container">
                            <form class="new_user_form inline-input" />
                                <div class="span12 field-box">
                                    <label>用户名:</label>
                                    <input class="span9" type="text" name="add-name"/>
                                </div>
                                
                                <div class="span12 field-box">
                                    <label>密码:</label>
                                    <input class="span9" type="password" name="add-password"/>
                                </div>
                                
                                <div class="span7 field-box actions">
                                		<input type="button" class="btn-glow primary" value="创建" style="width: 100px;" @click="addUser"/>                            
                                </div>
                            </form>
                        </div>
                    </div>

                    
                </div>
            </div>
        </div>
	</div>
</template>

<script>
export default{
        /* eslint-disable */
        data(){
            return{
                
            }
        },
        methods: {
        	addUser: function (){
        		var qs = require('qs');
            	this.$axios.post('users',qs.stringify({
  					"username": $("input[name='add-name']").val(),
  					"password": $("input[name='add-password']").val()
 				}),{
                /*params:{  //get请求在第二个位置，post在第三个位置
                    ID:'c02da6e9-a334-4e41-b842-c59eb7d0d3f3'
                },*/
                //设置头
                headers:{  
                    'content-type':'application/x-www-form-urlencoded'
                },
                auth: {
                    username: 'admin',
                    password: 'admin'
                }
            }).then(res=>{
                //this.users = res.data.data
                //console.log(res);
                this.$router.replace({ path: '/xy1'})
            })
            .catch(err=>{
                alert("请重新输入用户名！");
            })
        	}
        }
    }
</script>
<style>
	
</style>