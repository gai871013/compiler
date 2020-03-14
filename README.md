# 这是一个很笨的加密器
## 加密原理
我们可以经常在某些经过加密文件的php文件代码格式大体如下：
```php
xxx_loader_lable
<?php
if(!function_exists("xxx_loader")){
   die('xxx_loader not install');
}
//encrypt part
xxxxxxxxxxx
```

以swoole_loader为例子
````
SWOOLEC <?php extension_loaded('swoole_loader') or die(' Loader ext not installed');?>7140d79e0f5295e3cac6150978f0ebc17da88dda       h                                      ‡KI;JOyyu^r(KKJWQLC!I$TCXJxIJ/.Q\s/}s7}sIKJLNIKI;JOy3m^r(wKKJWQLC!I$TCXJxIJ/.Q\s/}s7}sIKJLN‡KI;JOyzu^?(wKKJWQÔ≥ºÈ!q<TCXJxIJ/.Q\s/}s7}sIKJLNHKI;JOy{u^r(wKKJWQLC![$TΩßË‚JxIJ/.Q\s/}s7}sI¥µ≥±HKI;JOyõXt^r(wJLJWQ
LCÈ‚ﬁ‚I/TCXHxIJ..QLs/}r7}sIKJLN0-I;JOy{u^r(wKKJWQLC!I$TCXJxIJ/.Q4k/}s7}s°KJLN∞KI;JOy{u^r(wKKJWQLC!I$TCXIxIJ)(QÏ(˜oŸŒÙ«jKJLNgj&998wF|2gk0;"'~\% snD39LeT¿'HX…V¨QQ$x/}s7}sIKJLNIKI;J_yu^r(w#KJWQLC!I$TCXKxIJ(.QDs/}ã»ÇåôKJLN@KI3JOysu^r(wKKJWQa%!H$TDXRxIJ◊—ÈÆde/}s7}sMOJLN@KI;JOy{u^r(wKKJWQLC!Y$TΩßË‚JxIJ/.Q\s/}s7}sA¥µ≥±HKI;JOy{u^r(wKKJWQLC!I$TCXJxIJ/.Q\s/}s7}sIKJLNHKI;JOy{u^r(wKKJWQLC!I$TCXJxIJ/.Q\s/}s7}sIKJLN0?ÀU∏5Oy˚TíBÒWw√6ü»5WQÄm√
íb!—ïH¿'ÍY…V¨QQ\s/}s7}sIKJLNHKI;JOy{u^r(wKKJWQLC!I$TCXJxIJ/.Q\s/}s7}sIKJLNHKI;JOy”t^r(wLJWQLC!K$TCY"uIJ/.Q¥r/}s7}sIKJLNHKI;JOy{u^r(wKKJWQLCíb!a)TCXJxIJ..Q\s/}s7}sIKJLNHKI;JOy{u^r(wKKJWQ∏MC!X$TWXJxIJ/.Q£å–Çr7}s±KJLNXKI∏5Oy{u^r(wKKJWQLC!I$TCXJxIJ/.Q^s/}s6|{1KJLN†KI;JOy{u^r(wJJJWQ∞BC!I$TCXNxIJ¨QQ§~/}s7}sHKJLNêKI;JOy{u^r(wKKJWQLC!I$TCX‚yIJ/.QEs/}o7}sIKJLN∑·¥∂9JOy√x^r(w[»5WQLC!I$TCXJxIJ/.Q\s/}s7}sIKJLNJKI;KNqÎz^r(w£KJWQLC!I$TCXJxIJ/.Q\s/}s7}sK»5LNKI;JOy{u^s(wKKJWQLC!I$TCXJxIJ/.Q\s/}s7}s·KJLNiKIJOy{u^r(w¥Ë‡‡JJWQ0CC!Y$T¿'JxIJ/.Q\s/}s7}sIKJLNHKI;JOy{u^r(wIKKVYÄ\C!°%TCXJxIJ/.Q]s/}r7}s˘KJLNHKI;JOyu^ÒWw[KJWQLC!°4TCXJxIJ/.Q\s/}s7}sIKJLNHKI;JOy”t^r(wbgJWQLC!∂€Í´AXöwIJ/.QLs/}H}sIKJLNHKI;JOy{u^r(wKKJWQLC!K$TCYÍiIJ/.Q¥r/}s7}sIKJLNHKI;JOy{u^r(wKKJWQLCíb!)5TCXJxIJ..Q\s/}s7}sIKJLNHKI;JOy{u^r(wKKJWQ∏MC!x$TwXJxIJ/.Q£å–Çr7}syKJLNXKI∏5Oy{u^r(wKKJWQLC!I$TCXJxIJ/.Q^s/}s6|{ÈKJLN†KI;JOy{u^r(wJJJWQ–^C!I$TCXNxIJ¨QQ|a/}s7}sHKJLN∞KI;JOy{u^r(wKKJWQLC!I$TCX‚yIJ/.Qes/}O7}sIKJLN∑·¥∂9JOyõd^r(w[»5WQLC!I$TCXJxIJ/.Q\s/}s7}sIKJLNJKI;KNqªf^r(w£KJWQLC!I$TCXJxIJ/.Q\s/}s7}sK»5LN»
KI;JOy{u^s(wKKJWQLC!I$TCXJxIJ/.Q\s/}s7}s·KJLN	KIJOy{u^r(w¥Ë‡‡JJWQX_C!Y$T¿'JxIJ/.Q\s/}s7}sIKJLNHKI;JOy{u^r(wIKKVY»XC!°%TCXJxIJ/.Q]s/}r7}sIKJLNHKI;JOyu^ÒWwKJWQLC!	1TCXJxIJ/.Q\s/}s7}sIKJLNHKI;JOy”t^r(wJWQLC!∂€Í´AXZlIJ/.QLs/}H}sIKJLNHKI;JOy{u^r(wKKJWQLC!a$TC\ínIJ/.Q\s/}s7}s°KJLNpKI;NOyCb^r(wKKJWQ¯MC!$TC\“oIJ/.Q\s/}s7}s°KJLNKI;NOyÉb^r(wKKJWQ¯MC!∂€Í´ºßË‚µá∂µ–—ÈÆ£å–Çå»ÇåH¥µ≥±P>ÀU∏5Oy{u^ç◊‡àeªŸ+≠c5É`À
íb!°%TCX[xIJ–—ÈÆ⁄¢m¢é¿ø√	KJLNIKI=LOy˝§PÅèﬂ›«PKJWQu-0objNr%AI7,5gq#;CGu42 J}H}sHMLLNN£4
````

这个文件。正常情况下,php是无法解析的。但是呢，zend_vm的一些接口，允许我们载入某些文件的时候，对文件进行预处理。因此我的拓展需要做的事情就是，如果遇到这样格式的文件，那么我把他解析为以下两部分：
- 部分1
```
<?php
if(!function_exists("xxx_loader")){
   die('xxx_loader not install');
}
```
- 部分2
```
//encrypt part
xxxxxxxxxxx
```

因此，code就是我经过加密后的目标字符串，显然，我们需要完成的一个步骤就是、字符串到代码的转变。而这个时候，如果有敏感的同学，就会想到一个东西，那就是
```eval()```。因此以上代码等价于：
```
<?php
if(!function_exists("xxx_loader")){
   die('xxx_loader not install');
}
eval(encrypt part);
```

但是实际上，并没有这么简单，如果我需要实现对机器授权的限制，那么应该是这样的。
```
$info = xxx_loader->decode(encrypPart);
$license = $info->licenseCheck();
if($license){
    eval($info->realyCode);
}
```

因此，如何保护我这个xxx_loader的实现逻辑，或者是加密秘钥，成为了代码加解密的关键。但是用php的话，容易出现，被逆向比如目前场景的php混淆，很容易破解。
因此就有人提出想法，如果我把这个加密的函数协程php拓展编译成so动态库文件，然后so在做加壳混淆，不就完美的解决了吗。毕竟、so加壳混淆的方案，可是非常成熟的。好了，我的加密拓展，就是这样的思路。

## 实现步骤
- c版本。c版本我们也会实现并开源，且教大家如何对自己编译出来的so文件进行加壳混淆。

## 部分测试
```
var_dump(extension_loaded('easy_complier'));

var_dump(easy_complier_decrypt('$a = new \stdclass();return $a;'));
```

## 弊端
- 问题：通过对zend_compile_file的hook可以得到完整的代码
- 解决方案：替换zend_compile_file，然后对生成的opcode进行指令插花，混淆

## 参考资料
- https://github.com/jvoisin/snuffleupagus/
