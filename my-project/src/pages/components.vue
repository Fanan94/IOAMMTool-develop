<template>
	<!-- main container -->
	<div>
		<div class="container-fluid">
			<div id="pad-wrapper" class="users-list">
				<div class="row-fluid header">
					<h3>组件</h3>
					<div class="span10 pull-right">
						<input type="text" class="span5 search" placeholder="Type a component's name..." />


						<div class="ui-dropdown">
							<div class="head" data-toggle="tooltip" title="Click me!">
								Filter components
								<i class="arrow-down"></i>
							</div>
							<div class="dialog">
								<div class="pointer">
									<div class="arrow"></div>
									<div class="arrow_border"></div>
								</div>
								<div class="body">
									<p class="title">
										Show users where:
									</p>
									<div class="form">
										<select>
											<option />Name
											<option />Email
											<option />Number of orders
											<option />Signed up
											<option />Last seen
										</select>
										<select>
											<option />is equal to
											<option />is not equal to
											<option />is greater than
											<option />starts with
											<option />contains
										</select>
										<input type="text" />
										<a class="btn-flat small">Add filter</a>
									</div>
								</div>
							</div>
						</div>

						<router-link to="/addComponent" class="btn-flat success pull-right">
							<span>&#43;</span>
							新增
						</router-link>

						<!--<router-link to="/deletComponent" class="btn-flat success pull-right ">-->
							<!--<span>&#43;</span>-->
							<!--删除-->
						<!--</router-link>-->
						<!-- <router-link to="/xy1">
                            <i class="icon-home"></i>
                            <span>XY1</span>
                        </router-link> -->
					</div>
				</div>

				<!-- Users table -->
				<div class="row-fluid table">
					<table class="table table-hover">
						<thead>
						<tr>
							<th class="span4 sortable">
								组件名称
							</th>
							<th class="span3 sortable">
								<span class="line"></span>版本
							</th>
							<th class="span3">
								<span class="line"></span>大小
							</th>
							<th class="span3">
								<span class="line"></span>描述
							</th>
						</tr>
						</thead>
						<tbody>
						<!-- row -->
						<tr class="first" v-for="(user,index) in users" :key="index">
							<td>
								{{user.username}}
							</td>
							<td class="description">
								{{user.password}}
							</td>
							<td>
								<span class="label label-success">Active</span>
								<ul class="actions">
									<li><a href="#">修改</a></li>
									<li class="last"><a href="#">删除</a></li>
								</ul>
							</td>
						</tr>
						<!-- row -->

						</tbody>
					</table>
				</div>
				<div class="pagination pull-right">
					<ul>
						<li><a href="#">&#8249;</a></li>
						<li><a class="active" href="#">1</a></li>
						<li><a href="#">2</a></li>
						<li><a href="#">3</a></li>
						<li><a href="#">4</a></li>
						<li><a href="#">5</a></li>
						<li><a href="#">&#8250;</a></li>
					</ul>
				</div>
				<!-- end users table -->
			</div>
		</div>
		<hr/>
		<div>
			{{users}}
		</div>
	</div>
</template>
</script>
<style>

</style>
