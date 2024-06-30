<footer class="footer">
	<div class="container">
		<div class="row">
			<div class="footer-col">
				<h4>myself</h4>
				<ul>
					<li><a href="#">about me</a></li>
					<li><a href="#">skills</a></li>
					<li><a href="#">achivements</a></li>
					<li><a href="#">hobbies and interests</a></li>
					<li><a href="#">my dev workflow</a></li>
				</ul>
			</div>
			<div class="footer-col">
				<h4>projects</h4>
				<ul>
					<li><a href="#">game of life</a></li>
					<li><a href="#">ecosight</a></li>
					<li><a href="#">particle life</a></li>
					<li><a href="#">streamer hub</a></li>
				</ul>
			</div>
			<div class="footer-col">
				<h4>contact me</h4>
				<ul>
					<li><a href="#">email</a></li>
					<li><a href="#">telegram</a></li>
					<li><a href="#">discord</a></li>
				</ul>
			</div>
			<div class="footer-col">
				<h4>follow me</h4>
				<div class="social-links">
					<a href="#"><i class="fab fa-instagram"></i></a>
					<a href="#"><i class="fab fa-github"></i></a>
				</div>
			</div>
		</div>
	</div>
</footer>

<style>
	@import '@fortawesome/fontawesome-free/css/all.min.css';

	.container {
		max-width: 1170px;
		margin: auto;
	}
	.row {
		display: flex;
		justify-content: start;
		flex-wrap: wrap;
	}
	ul {
		list-style: none;
	}
	.footer {
		background-color: #1e1e2e;
		padding: 70px 0;
		z-index: 99;
	}
	.footer-col {
		width: 25%;
		padding: 0 15px;
	}
	.footer-col h4 {
		font-size: 18px;
		color: #cdd6f4;
		text-transform: capitalize;
		margin-bottom: 35px;
		font-weight: 500;
		position: relative;
	}
	.footer-col h4::before {
		content: '';
		position: absolute;
		left: 0;
		bottom: -10px;
		background-color: #89dceb;
		height: 2px;
		box-sizing: border-box;
		width: 50px;
	}
	.footer-col ul li:not(:last-child) {
		margin-bottom: 10px;
	}
	.footer-col ul li a {
		font-size: 16px;
		text-transform: capitalize;
		color: #ffffff;
		text-decoration: none;
		font-weight: 300;
		color: #a6adc8;
		display: block;
		transition: all 0.3s ease;
	}
	.footer-col ul li a:hover {
		color: #ffffff;
		padding-left: 8px;
	}
	.footer-col .social-links a {
		display: inline-block;
		height: 40px;
		width: 40px;
		background-color: rgba(255, 255, 255, 0.2);
		margin: 0 10px 10px 0;
		text-align: center;
		line-height: 40px;
		border-radius: 50%;
		color: #bac2de;
		transition: all 0.5s ease;
	}
	.footer-col .social-links a:hover {
		color: #24262b;
		background-color: #bac2de;
	}

	/*responsive*/
	@media (max-width: 507px) {
		.footer-col {
			width: 50%;
			margin-bottom: 30px;
		}
	}
	@media (max-width: 430px) {
		.footer-col {
			width: 100%;
		}
	}
</style>
