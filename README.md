# request.post
微信的post请求的封装

直接原文贴起~~~~




// let host = {

        request: "https://www.nazhua.net/", //请求域名
	
    }


 
 if (ajaxJson.isLoading) { //为ture 显示loading
 
        wx.showLoading({
	
            title: '加载中',
        })
    }

 post : function (ajaxJson) {
 
    wx.request({
        url: host.request + ajaxJson.url,
        data: ajaxJson.data,
        method: ajaxJson.method != undefined ? jaxJson.method : "post",
        dataType: "json",
        success(res) {
            ajaxJson.success(res)
        },
        complete: function(res) {
            if (ajaxJson.isLoading == true && typeof ajaxJson.success === "function") {
                wx.hideLoading();
            }
    })
}

    // 请求表达式：1.把上面的放到 app.js 里面；
    //            2. 在需要请求的页面的js里 page 函数外面申明常量  const app = getApp();
 ``//             3. 那么请求表达式为
                app.post({
                    url:'admin/asd', //里面内容是你上面 host 里面网址的后续 。
                    data:{ a: 1},   // 这里的  data是传送数据的  。data可以有，也可以没有。
                    isLoading:true, //这里的isLoding 如果不写就不会出现请求等待的图标
                    success:(res)=>{
                                              //这里的res就可以直接拿到用了
                         }
                    })
              //  请求方法为post  如果想改就在里面加一个 method：get 之类的。
	      
			  
