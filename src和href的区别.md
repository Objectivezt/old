# Some-essays
	<section>
		<h1>src和href的区别</h1>
		<h4>src是用于替换当前元素，href是用于当前文本和引用资源之间确立联系<h4>
		<p>src是source的缩写，是指向外部资源位置，并把指向内容嵌入到文档中当前标签所在位置；在请求src资源会讲其指向资源下载并应用到文档内，例如，js脚本，img图片和frame等元素。<p>
	   <p>href是Hypertext Reference的缩写，指向资源所在位置，建立和当前元素和当前文档之间的链接。<p>
	   <ul>
	   		<li>
				<p>需要注意的是：</p>
				`<script src = "JavaScript.js"></script>`
				`<link href = "Css.css" rel="stylesheet">`
			</li>

			<li>
				<p>这两种的执行效果机制：</p>
				1.首先，当文件解析script时候就会停止其他元素的加载与处理，一直到该资源加载编译执行完毕。所以一般script标签一般会放在文件的底部而不是头部
				2.link会识别css文件，就会并行下载资源但不会停止对文档的处理。
			</li>
		</ul>
	</section>
