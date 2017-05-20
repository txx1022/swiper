<?php
error_reporting(E_ALL || ~E_NOTICE);
header("Content-type:text/html; charset=utf-8");
require_once "sdk/jssdk.php";
$jssdk = new JSSDK("wxb4ea8558c4d84e78", "77ce67603fe19dcd6b30ae39e19bf48f");
$signPackage = $jssdk->GetSignPackage();
?>
<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no" />
<title>无标题文档</title>
<script src="http://res.wx.qq.com/open/js/jweixin-1.0.0.js"></script>
<script>
wx.config({
    debug: true,// 开启调试模式,调用的所有api的返回值会在客户端alert出来，若要查看传入的参数，可以在pc端打开，参数信息会通过log打出，仅在pc端时才会打印。
    appId: '<?php echo $signPackage["appId"];?>',
    timestamp: <?php echo $signPackage["timestamp"];?>,
    nonceStr: '<?php echo $signPackage["nonceStr"];?>',
    signature: '<?php echo $signPackage["signature"];?>',
    jsApiList: [
	 'checkJsApi',
        'onMenuShareTimeline',
        'onMenuShareAppMessage',
        'onMenuShareQQ',
        'onMenuShareWeibo',
        'hideMenuItems',
        'showMenuItems',
        'hideAllNonBaseMenuItem',
        'showAllNonBaseMenuItem',
        'translateVoice',
        'startRecord',
        'stopRecord',
        'onRecordEnd',
        'playVoice',
        'pauseVoice',
        'stopVoice',
        'uploadVoice',
        'downloadVoice',
        'chooseImage',
        'previewImage',
        'uploadImage',
        'downloadImage',
        'getNetworkType',
        'openLocation',
        'getLocation',
        'hideOptionMenu',
        'showOptionMenu',
        'closeWindow',
        'scanQRCode',
        'chooseWXPay',
        'openProductSpecificView',
        'addCard',
        'chooseCard',
        'openCard'
	] // 必填，需要使用的JS接口列表，所有JS接口列表见附录2
});

wx.ready(function(){
    var btn=document.getElementById("getphone");
	btn.onclick=function(){
		wx.chooseImage ({
            success : function(res){
                var localIds = res.localIds; 
                // 返回选定照片的本地ID列表，localId可以作为img标签的src属性显示图片
            }
        });
	}
})
</script>
</head>

<body>
<button id="getphone">拍照</button>
</body>
</html>
