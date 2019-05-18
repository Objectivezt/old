# Some-essays
记录自己的成长
    <header>JavaScript的跨域搬运整理摘自（http://f2e.me/200904/cross-scripting）访问不稳定</header>
    <section>
        <table>
            <tr>
                <td>URL</td>
                <td>说明</td>
                <td>是否允许通信</td>
            </tr>
            <tr>
                <td>http://www.Obj.com/a.js </td>
                <td rowspan="2">同一域名下</td>
                <td rowspan="2">允许</td>
            </tr>
            <tr>
                <td>http://www.Obj.com/b.js </td>
            </tr>
            <tr>
                <td>http://www.Obj.com/lab/a.js</td>
                <td rowspan="2">同一域名下不同文件夹</td>
                <td rowspan="2">允许</td>
            </tr>
            <tr>
                <td>http://www.Obj.com/script/b.js</td>
            </tr>
            <tr>
                <td>http://www.Obj.com:8000/a.js </td>
                <td rowspan="2">同一域名，不同端口</td>
                <td rowspan="2">不允许</td>
            </tr>
            <tr>
                <td>http://www.Obj.com/b.js  </td>
            </tr>
            <tr>
                <td>http://www.Obj.com/a.js </td>
                <td rowspan="2"> 同一域名，不同协议</td>
                <td rowspan="2">不允许</td>
            </tr>
            <tr>
                <td>https://www.Obj.com/b.js </td>
            </tr>
            <tr>
                <td>http://www.Obj.com/a.js </td>
                <td rowspan="2">域名和域名对应ip</td>
                <td rowspan="2">不允许</td>
            </tr>
            <tr>
                <td>http://192.168.92.11/b.js </td>
            </tr>
            <tr>
                <td>http://www.Obj.com/a.js</td>
                <td rowspan="2"> 主域相同，子域不同</td>
                <td rowspan="2">不允许</td>
            </tr>
            <tr>
                <td>http://script.a.com/b.js </td>
            </tr>
            <tr>
                <td>http://www.Obj.com/a.js　</td>
                <td rowspan="2"> 同一域名，不同二级域名</td>
                <td rowspan="2">不允许（cookie这种情况下也不允许访问）</td>
            </tr>
            <tr>
                <td>http://a.com/b.js </td>
            </tr>
            <tr>
                <td>http://www.cnblogs.com/a.js　</td>
                <td rowspan="2"> 不同域名</td>
                <td rowspan="2">    不允许</td>
            </tr>
            <tr>
                <td>http://www.Obj.com/b.js  </td>
            </tr>
        </table>
    </section>

