# Some-essays
记录自己的成长
     <header><h1>Jquery学习中的一些笔记上传</h1></header>
    <section>
        <ul>
            <li>
                <h2>jquery对象和Dom对象的转化</h2>
                <p>使用函数$(dom对象)</p>
                <code>
                    function foo(){
                        var obj = document.getElementById('divs');
                        var $obj = $(obj)
                        $obj.html('hello Jquery')
                    }
                </code>
            </li>
            <li>
                <h2>Dom对象和jquery对象的转化</h2>
                <p>方法一$obj.get(0)</p>
                <code>
                    function foo(){
                        var $obj = $('#divs');
                        var obj = $obj.get(0)
                        obj.innerHTML = 'hello perl'
                    }
                </code>
            </li>
            <li>
                <h2>Dom对象和jquery对象的转化</h2>
                <p>方法二$obj.get()[0]</p>
                <code>
                    function foo(){
                        var $obj = $('#divs');
                        var obj = $obj.get()[0]
                        obj.innerHTML = 'hello perl'
                    }
                </code>
            </li>
            <li>
                <h2>Jquery基础选择器</h2>
                <p>ID选择器</p>
                <code>$("#divs").css('color','red')
                </code>
                 <p>类选择器</p>
                <code>$('.divc').css('color','green')
                </code>
                <p>元素选择器</p>
                <code>$('div').css('color','blue')
                </code>
                <p>合并选择器</p>
                <code>$('#divs,divsl').css('font-size','18px')
                </code>
                <p>通配符选择器</p>
                <code>$('*').css('background','red')
                </code>
            </li>
            <li>
                <h2>Jquery的层次选择器</h2>
                <p>所有后代</p>
                <code>$('#divc div')
                </code>
                <p>子代选择（不考虑后代）</p>
                <code>$('#divs>div')
                </code>
                <p>下一个兄弟选择（不考虑子代）</p>
                <code>$('#div+div')
                </code>
                <p>所有兄弟节点</p>
                <code>$("#divs~div")
                </code>
            </li>
            <li>
                <h2>JQuery过滤选择器</h2>
                <p>第一行过滤选择器</p>
                <code>
                $('#div span:first')
                </code>
                <p最后一行过滤选择器</p>
                <code>
                $('#div span:last')
                </code>
                <p>偶数过滤选择器</p>
                <code>
                $('#div span:even')
                </code>
                <p>奇数行过滤选择器</p>
                <code>
                $('#div span:odd')
                </code>
                 <p>等于下标过滤选择器（0开始）</p>
                <code>
                $('#div span:eq')
                </code>
                <p>大于下标过滤选择器（0开始）</p>
                <code>
                $('#div span:gt')
                </code>
                <p>小于下标过滤选择器（0开始）</p>
                <code>
                $('#div span:lt')
                </code>
                 <p>满足删除过滤选择器（0开始）</p>
                <code>
                $('#div span:not('#divss')')
                </code>
            </li>
            <li>
                <h2></h2>
                <p></p>
                <code>
                </code>
            </li>
        </ul>
    </section>
