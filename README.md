# jquery1
오랜만에 제이쿼리 쓰이는 거

<script>
	jQuery(document).ready(function(){
		//setTimeout(function(){
			//calling API for streaming tickers
			nonfootergetAllTradingListMarketDD();
		//}, 3000);
	});

	function nonfootergetAllTradingListMarketDD(){
	    jQuery.get("https://stream.paybito.com/StreamingApi/rest/TrendsGraph24Hour", function(data){
	     
			   var result=JSON.parse(data);
			   var html='';
			   if(result!=null){
				//    console.log(event);
                //    console.log(result);

				
                var html='';
				// set usd trend list 
					var usdtradeList=result.usdtrendHistories;
					if(result.usdnetVolume!=null){
					  window.usd24HVolume=result.usdnetVolume;
					}else{
					  window.usd24HVolume='0.00';
					}
					
					window.usdRandomNoForLastPrice = Math.floor((Math.random() * 10) + 1);
					window.usdRandomNoForHourChange = Math.floor((Math.random() * 10) + 1);
					if(usdtradeList!=null){
						for(var i=0;i<usdtradeList.length;i++){

						  if(usdtradeList[i].currency=='BTC'){
								var coin='Bitcoin';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/bitcoin.svg" alt="bitcoin">';
								// $('.btcPriceBox').html('$' + usdtradeList[i].ctp);
								// if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								//   $('.btcRoc').html('<strong class="small text-red">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }else{
								//   $('.btcRoc').html('<strong class="small text-green">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }
							  
							}
							if(usdtradeList[i].currency=='ETH'){
								var coin='Ethereum';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/ether.svg" alt="ether">';
								// $('.ethPriceBox').html('$' + usdtradeList[i].ctp);
								// if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								//   $('.ethRoc').html('<strong class="small text-red">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }else{
								//   $('.ethRoc').html('<strong class="small text-green">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }
							}
							if(usdtradeList[i].currency=='BCH'){
								var coin='Bitcoin Cash';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/bitcoin-cash.svg" width="32px" height="32px" alt="bitcoin-cash">';
								// $('.bchPriceBox').html('$' + usdtradeList[i].ctp);
								// if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								//   $('.bchRoc').html('<strong class="small text-red">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }else{
								//   $('.bchRoc').html('<strong class="small text-green">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }
							}
							if(usdtradeList[i].currency=='USD'){
								var coin='US Dollar';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/usd.svg" alt="usd">';
							}
							if(usdtradeList[i].currency=='LTC'){
								var coin='Litecoin';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/litecoin.svg" alt="litecoin">';
							}
							if(usdtradeList[i].currency=='HCX'){
								var coin='HCX';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/hcx.png"width="32px" height="32px" alt="hcx">';
								// $('.hcxPriceBox').html('$' + usdtradeList[i].ctp);
								// if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								//   $('.hcxRoc').html('<strong class="small text-red">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }else{
								//   $('.hcxRoc').html('<strong class="small text-green">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }
							}
                            if(usdtradeList[i].currency=='ETC'){
                                var coin='ETC';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/etc.png" width="32px" height="32px" alt="hcx">';
                            }
                            if(usdtradeList[i].currency=='BSV'){
                                var coin='BSV';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/bsv.png" width="32px" height="32px" alt="hcx">';
                            }
                            if(usdtradeList[i].currency=='DIAM'){
                                var coin='DIAM';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/diam.svg" width="32px" height="32px" alt="Diam">';
                            }
                            if(usdtradeList[i].currency=='ADA'){
                                var coin='ADA';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/ada.png" width="32px" height="32px" alt="ADA">';
                            }
                            if(usdtradeList[i].currency=='EOS'){
                                var coin='EOS';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/eos.png" width="32px" height="32px" alt="EOS">';
                            }
                            if(usdtradeList[i].currency=='XRP'){
                                var coin='XRP';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/xrp.png" width="32px" height="32px" alt="XRP">';
                            }
                            if(usdtradeList[i].currency=='HBAR'){
                                var coin='HBAR';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/hbar.png" width="32px" height="32px" alt="HBAR">';
                            }

                            if(usdtradeList[i].currency=='LINK'){
                                var coin='LINK';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/link.svg" width="32px" height="32px" alt="LINK">';
                            }
                            if(usdtradeList[i].currency=='BAT'){
                                var coin='BAT';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/bat.png" width="32px" height="32px" alt="BAT">';
                            }
                            if(usdtradeList[i].currency=='KICKS'){
                                var coin='KICKS';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/kicks-logo.png" width="32px" height="32px" alt="KICKS">';
                            }
							if(usdtradeList[i].currency=='CAR'){
                                var coin='CARRERA';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/car-coin.png" width="32px" height="32px" alt="CAR">';
                            }

							  if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								  var rocTextClass='text-red';
							  }else{
								  var rocTextClass='text-green';
							  }

							  if(usdtradeList[i].action=='buy'){
								  var ctpTextClass='text-green';
							  }

							  if(usdtradeList[i].action=='sell'){
								  var ctpTextClass='text-red';
							  }
                			var usdnetvol=usdtradeList[i].volume;
                			str = usdnetvol.replace(/[$]/gi,'');
							  /* for banner slider */
							if (usdtradeList[i].currency == 'BTC') {
								$('.btcusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.btcusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'ETH') {
								$('.ethusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.ethusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'HCX') {
								$('.hcxusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.hcxusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'BCH') {
								$('.bchusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.bchusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'XRP') {
								$('.xrpusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.xrpusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'BSV') {
								$('.bsvusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.bsvusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'LTC') {
								$('.ltcusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.ltcusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'EOS') {
								$('.eosusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.eosusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'ADA') {
								$('.adausd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.adausd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'LINK') {
								$('.linkusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.linkusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'BAT') {
								$('.batusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.batusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'HBAR') {
								$('.hbarusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.hbarusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'UBU') {
								$('.ubuusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.ubuusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
							if (usdtradeList[i].currency == 'CAR') {
								$('.carusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.carusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
							/* for banner slider */

						}
					}else{
					  html+='';
					}	
					
					//$('#usdMarketBodydd').html(html);
					//$('.custom-slick').html(html);
					                   					
			   }
          		 		  
			});  
       
	}
</script>
<script>
	jQuery(document).ready(function(){
		//setTimeout(function(){
			//calling API for streaming tickers
			getAllTradingListMarketDD();
		//}, 3000);
	});

	function getAllTradingListMarketDD(){
	    var url='https://stream.paybito.com/StreamingApi/rest/GetAllTradeGraph24Hours';
	     
       var source = new EventSource(url);
       source.close();
       if(typeof(EventSource) !== "undefined") {
         var source = new EventSource(url);
         source.onmessage = function(event) 
		    {
			   var result=JSON.parse(event.data);
			   var html='';
			   if(result!=null){
				//    console.log(event);
                //    console.log(result);

				
                var html='';
				// set usd trend list 
					var usdtradeList=result.usdtrendHistories;
					if(result.usdnetVolume!=null){
					  window.usd24HVolume=result.usdnetVolume;
					}else{
					  window.usd24HVolume='0.00';
					}
					
					window.usdRandomNoForLastPrice = Math.floor((Math.random() * 10) + 1);
					window.usdRandomNoForHourChange = Math.floor((Math.random() * 10) + 1);
					if(usdtradeList!=null){
						for(var i=0;i<usdtradeList.length;i++){

						  if(usdtradeList[i].currency=='BTC'){
								var coin='Bitcoin';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/bitcoin.svg" alt="bitcoin">';
								// $('.btcPriceBox').html('$' + usdtradeList[i].ctp);
								// if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								//   $('.btcRoc').html('<strong class="small text-red">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }else{
								//   $('.btcRoc').html('<strong class="small text-green">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }
							  
							}
							if(usdtradeList[i].currency=='ETH'){
								var coin='Ethereum';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/ether.svg" alt="ether">';
								// $('.ethPriceBox').html('$' + usdtradeList[i].ctp);
								// if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								//   $('.ethRoc').html('<strong class="small text-red">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }else{
								//   $('.ethRoc').html('<strong class="small text-green">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }
							}
							if(usdtradeList[i].currency=='BCH'){
								var coin='Bitcoin Cash';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/bitcoin-cash.svg" width="32px" height="32px" alt="bitcoin-cash">';
								// $('.bchPriceBox').html('$' + usdtradeList[i].ctp);
								// if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								//   $('.bchRoc').html('<strong class="small text-red">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }else{
								//   $('.bchRoc').html('<strong class="small text-green">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }
							}
							if(usdtradeList[i].currency=='USD'){
								var coin='US Dollar';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/usd.svg" alt="usd">';
							}
							if(usdtradeList[i].currency=='LTC'){
								var coin='Litecoin';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/litecoin.svg" alt="litecoin">';
							}
							if(usdtradeList[i].currency=='HCX'){
								var coin='HCX';
								var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/hcx.png"width="32px" height="32px" alt="hcx">';
								// $('.hcxPriceBox').html('$' + usdtradeList[i].ctp);
								// if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								//   $('.hcxRoc').html('<strong class="small text-red">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }else{
								//   $('.hcxRoc').html('<strong class="small text-green">'+parseFloat(usdtradeList[i].roc).toFixed(2)+'%</strong>');
								// }
							}
                            if(usdtradeList[i].currency=='ETC'){
                                var coin='ETC';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/etc.png" width="32px" height="32px" alt="hcx">';
                            }
                            if(usdtradeList[i].currency=='BSV'){
                                var coin='BSV';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/bsv.png" width="32px" height="32px" alt="hcx">';
                            }
                            if(usdtradeList[i].currency=='DIAM'){
                                var coin='DIAM';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/diam.svg" width="32px" height="32px" alt="Diam">';
                            }
                            if(usdtradeList[i].currency=='ADA'){
                                var coin='ADA';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/ada.png" width="32px" height="32px" alt="ADA">';
                            }
                            if(usdtradeList[i].currency=='EOS'){
                                var coin='EOS';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/eos.png" width="32px" height="32px" alt="EOS">';
                            }
                            if(usdtradeList[i].currency=='XRP'){
                                var coin='XRP';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/xrp.png" width="32px" height="32px" alt="XRP">';
                            }
                            if(usdtradeList[i].currency=='HBAR'){
                                var coin='HBAR';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/hbar.png" width="32px" height="32px" alt="HBAR">';
                            }

                            if(usdtradeList[i].currency=='LINK'){
                                var coin='LINK';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/link.svg" width="32px" height="32px" alt="LINK">';
                            }
                            if(usdtradeList[i].currency=='BAT'){
                                var coin='BAT';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/bat.png" width="32px" height="32px" alt="BAT">';
                            }
                            if(usdtradeList[i].currency=='KICKS'){
                                var coin='KICKS';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/kicks-logo.png" width="32px" height="32px" alt="KICKS">';
                            }
			    if(usdtradeList[i].currency=='CAR'){
                                var coin='CARRERA';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/car-coin.png" width="32px" height="32px" alt="CAR">';
                            }
			    if(usdtradeList[i].currency=='LEO'){
                                var coin='LEO';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/leo.png" width="32px" height="32px" alt="CAR">';
                            }


							  if(parseFloat(usdtradeList[i].roc)<parseFloat(0)){
								  var rocTextClass='text-red';
							  }else{
								  var rocTextClass='text-green';
							  }

							  if(usdtradeList[i].action=='buy'){
								  var ctpTextClass='text-green';
							  }

							  if(usdtradeList[i].action=='sell'){
								  var ctpTextClass='text-red';
							  }
                			var usdnetvol=usdtradeList[i].volume;
                			str = usdnetvol.replace(/[$]/gi,'');
							  /* for banner slider */
							if (usdtradeList[i].currency == 'BTC') {
								$('.btcusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.btcusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'ETH') {
								$('.ethusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.ethusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'HCX') {
								$('.hcxusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.hcxusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'BCH') {
								$('.bchusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.bchusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'XRP') {
								$('.xrpusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.xrpusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'BSV') {
								$('.bsvusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.bsvusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'LTC') {
								$('.ltcusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.ltcusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'EOS') {
								$('.eosusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.eosusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'ADA') {
								$('.adausd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.adausd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'LINK') {
								$('.linkusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.linkusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'BAT') {
								$('.batusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.batusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'HBAR') {
								$('.hbarusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.hbarusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
	                        if (usdtradeList[i].currency == 'UBU') {
								$('.ubuusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.ubuusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
				if (usdtradeList[i].currency == 'CAR') {
								$('.carusd-lp').html("<font class='"+ctpTextClass+"'>"+usdtradeList[i].close_PRICE+"</font>");
								$('.carusd-change').html("<font class='"+rocTextClass+"'>"+parseFloat(usdtradeList[i].roc).toFixed(2)+"%</font>");
	                        }
				if(usdtradeList[i].currency=='LEO'){
                                var coin='LEO';
                                var coinImage='<img src="https://www.paybito.com/wp-content/themes/paybito-theme/images/coins/leo.png" width="32px" height="32px" alt="CAR">';
                            	}


							/* for banner slider */

						}
					}else{
					  html+='';
					}	
					
					//$('#usdMarketBodydd').html(html);
					//$('.custom-slick').html(html);
					                   					
			   }
          		 		  
            }
        }
	}
</script>

<script>
	jQuery(document).ready(function(){

		jQuery('.media-slider').owlCarousel({
	      loop: true,
	      items: 1,
	      slideSpeed: 2000,
	      nav:false,
	      dots:false,
	      autoplay: true,
	      thumbs: true,
	      thumbImage: true,
	      thumbContainerClass: 'owl-thumbs',
	      thumbItemClass: 'owl-thumb-item'
	    });

	    jQuery('.slick.marquee').slick({
	        speed: 5000,
	        autoplay: true,
	        autoplaySpeed: 0,
	        centerMode: true,
	        cssEase: 'linear',
	        slidesToShow: 1,
	        slidesToScroll: 1,
	        variableWidth: true,
	        infinite: true,
	        initialSlide: 1,
	        arrows: false,
	        buttons: false
	    });

	});
</script>
<script>
	$("#editbox").click(function(){
		//$(".product-cross").css("display","inline-block");
		$(".product-cross").toggleClass("boxshow");
	});
	/*$(".product-cross").click(function(){
		$(this).parents(".watchtable-box").addClass("hide");
	});*/
</script>

<script>
	/*$(document).ready(function(){
		console.log(document.cookie);
	});*/

/*function getCookie(userName) {
  var name = userName + "=";
  var ca = document.cookie.split(';');
  for(var i = 0; i < ca.length; i++) {
    var c = ca[i];
    while (c.charAt(0) == ' ') {
      c = c.substring(1);
    }
    if (c.indexOf(name) == 0) {
      return c.substring(name.length, c.length);
    }
  }
  return "";
}*/
</script>
<style>
.slick-slider {
    width: 100%;
    float: left;
}
.loadhide {display: none !important;}
</style>
<script>
$(window).on('load',function() {
  $('.custom-slick1').hide();
  setTimeout(function() {
	$('#loader').addClass('loadhide');
	$('.custom-slick1').show();
  }, 4000);

  page_loader();
});

function page_loader() {
	$('.loading-area').fadeOut(2000)
}
</script>

<script>
	$(window).on('load',function(){

    	//console.log(document.cookie);

		var cookie_username = readCookie('Username');
		var cookie_userid = readCookie('userId');   
		var cookie_token = readCookie('ssecca');   
		// window.cookie_username = cookie_username;
		// var localstorage_set_cookie_username=localStorage.setItem('localstorage_cookie_username', cookie_username);
		// console.log('localstorage ',localstorage_set_cookie_username);
		// var localstorage_get_cookie_username=localStorage.getItem('localstorage_cookie_username');
		// console.log('get localstorage ',localstorage_get_cookie_username);
		if( cookie_username != '' && cookie_username != null ){
			console.log(cookie_username);
			console.log(cookie_userid);
			console.log(cookie_token);
			

			$('.add-pair').css('display', 'block');
			$('.edit-pair').css('display', 'block');

			//SSO Menu
			$('.sso-menu').html("<li class='nav-item'><a href='#' class='nav-link' style='text-transform: capitalize;'>Hi "+cookie_username+"</a></li><li class='nav-item'><a href='javascript:void(0);' class='delcookie nav-link' >Logout</a></li>");
			//Fetch select option pair
			
			$.ajax({
				url: "https://accounts.paybito.com/api/home/getAllAssetpair",
				method: "GET",
				dataType: "json",
				crossDomain: true,
				contentType: "application/json; charset=utf-8",
				//data: JSON.stringify(account_details),
				cache: false,

				beforeSend: function (xhr) {
					xhr.setRequestHeader( "Authorization", "BEARER " + cookie_token );
				},                                    
				success: function (data) {
					// console.log(data); 
					// var result = JSON.parse(data);
					// console.log(data.assetPairList.error.error_data);
					// console.log(data.assetPairList.assetPairList);
					// var allassetPairList = data.assetPairList; 
					for (var i = 0; i < data.assetPairList.length; i++) {
						// console.log(data.assetPairList[i].assetPair);
						if(data.assetPairList[i].assetPair != 'BTC-USD' && data.assetPairList[i].assetPair != 'BCH-USD' && data.assetPairList[i].assetPair != 'ETH-USD' && data.assetPairList[i].assetPair != 'HCX-USD'){
							var replaceslshassetpairlist =data.assetPairList[i].assetPair.replace(/-/g, '/');
							var result = replaceslshassetpairlist.split("/");
							var onlycurrencyresult=result[result.length - 1]
							var option;
							option +='<option datapair="'+onlycurrencyresult+'" value="'+replaceslshassetpairlist+'">';
							option +=data.assetPairList[i].assetPair ;
							option +='</option>';
							$('#usdMarketBody1').html(option);
							// $('#usdMarketBody1').html('<option>'+data.assetPairList[i].assetPair+'</option>');
							// $("#usdMarketBody1").append($("#usdMarketBody1 option").remove().sort(function(a, b) {
							// 	var at = $(a).attr('datapair'), bt = $(b).attr('datapair');
							// 	return (at < bt)?1:((at > bt)?-1:0);
							// }));
						}
					}
					// console.log(data.assetPairList.assetPairList.assetPair); 
					// $("#usdMarketBody1") 
				},
				error: function (data) {
					console.log(data);
				}
			});

			//Fetch user specific watchlist pair
			$.ajax({
				url: "https://accounts.paybito.com/api/home/getUserWiseAssetWatchList?userId="+cookie_userid,
				method: "GET",
				dataType: "json",
				crossDomain: true,
				contentType: "application/json; charset=utf-8",
				//data: JSON.stringify(account_details),
				cache: false,

				beforeSend: function (xhr) {
					xhr.setRequestHeader( "Authorization", "BEARER " + cookie_token );
				},                                    
				success: function (data) {
					console.log(data);                                
					//console.log(data.userAssetWatchList.length);

					//var li = $('.watchtable-slider-1').find('.watchtable-box');
					var thumbLi = $('.watchtable-box');        

					for (var i = 0; i < data.userAssetWatchList.length; i++) {

						if( data.userAssetWatchList[i].USER_ID == cookie_userid ){ //specific user
							var f_curr_crypto = data.userAssetWatchList[i].ASSET;         		
							var f_curr = data.userAssetWatchList[i].ASSET.split('/'); 
							console.log('userassetlist-asset '+f_curr);                 	
							var optPair = f_curr[0].toLowerCase();
							console.log('OPT: '+optPair);

							$('.watchtable-box').each(function() {
								if (($(this).attr('data-pair') == optPair) && ($(this).children(".row").children(".col-sm-12").children(".numbers").children(".product-cross").attr('data-pair') == f_curr_crypto)){
									//console.log($(this).attr('data-pair')+'------from watchtable');
									$(this).removeClass('hide');
									$(this).addClass('countwatchbox');
									// if($(this).hasClass("countwatchbox")){
									// 	alert("This trading pair is already added to the Watchlist !");
									// }
									$(this).attr( "pair-id", data.userAssetWatchList[i].ID );
									$(this).find('.product-cross').attr( "pair-id", data.userAssetWatchList[i].ID );
								}
							});

						}

					}

				},
				error: function (data) {
					console.log(data);
					$('#pairmsg').html("<p style='color:green;text-align:center; width:100%;float:left;margin-top:15px;'>Please Login trade.paybito.com </p>");
				}
			});


			//adding user specific watchlist pair
			$(document).on('click', '#addpair', function(addpair){
				// $(this).parent(".form-group").siblings(".form-group").children("#usdMarketBody1").children('option:selected').addClass("data-type");
				addpair.preventDefault();
				var asset_pair = $('#usdMarketBody1').val();
				console.log("asset pair" + asset_pair);
				// console.log("asset pair without",+asset_pair.split('/'));
				// var arrlg=asset_pair.split('/');
				// console.log(arrlg);
				// console.log("asset pair without"+arrlg[1]);
				console.log("User ID" + cookie_userid);
				console.log("Cookie Token" + cookie_token);
				$('#pairmsg').html("<p style='color:green;text-align:center; width:100%;float:left;margin-top:15px;'>Please wait...</p>");

				var add_pair = { "userId": cookie_userid, "assetPair" : asset_pair, "action" :"INSERT" }


				$.ajax({
					url: "https://accounts.paybito.com/api/home/updateUserWiseAssetWatchList",
					method: "POST",
					dataType: "json",
					crossDomain: true,
					contentType: "application/json; charset=utf-8",
					data: JSON.stringify(add_pair),
					cache: false,

					beforeSend: function (xhr) {
						xhr.setRequestHeader( "Authorization", "BEARER " + cookie_token );
					},                                    
					success: function (data) {
						console.log('addpair ',data);
						console.log('addpair ',data.error);
						
						$('#pairmsg').html("<p style='color:green;text-align:center; width:100%;float:left;margin-top:15px;'>"+data.error.error_msg+"</p>");
						if((data.error.error_msg=='This trading pair is already in your Watchlist!') || (data.error.error_msg=='You have exceeded the maximum number of trading pairs that can be added to the Watchlist !')){

							// alert("stop reloading");
						}else{
							setTimeout(function(){
								location.reload();
							}, 1000); 
							// setTimeout(function(){
							// 	$("#watchtable-slider-wrap-inner").load(location.href+" #watchtable-slider-wrap-inner>*","");
							// }, 1000); 
						}
						// $('.watchtable-box').html("<p style='color:green;text-align:center; width:100%;float:left;margin-top:15px;'>"+data.error.error_msg+"</p>");
						// $(this).parent(".form-group").siblings(".form-group").children("#usdMarketBody1").children('option:selected').addClass("data-type");
						//  $(this).parent(".form-group").parents(".modal").addClass("new");
						// setTimeout(function(){
						//   location.reload();
						// }, 1000); 
						// $('.watchtable-box').each(function() { 
						// 	if ($(this).children(".row").children(".col-sm-12").children(".numbers").children(".product-cross").attr('data-pair') == asset_pair){
						// 		$(this).removeClass("hide");
						// 	}
						// });
						
												
					},
					error: function (data) {
						console.log(data);
					}
				});

			});

			//deleting user specific watchlist pair
			$(document).on('click', '.product-cross', function(delpair){

				delpair.preventDefault();
				var asset_pair = $(this).attr('data-pair');
				var asset_pairid = $(this).attr('pair-id');

				console.log(asset_pair);
				console.log(asset_pairid);

				//$('#pairmsg').html("<p style='color:green;text-align:center; width:100%;float:left;margin-top:15px;'>Please wait...</p>");

				var del_pair = {"id":asset_pairid,"userId":cookie_userid,"assetPair":asset_pair,"action":"DELETE"}


				$.ajax({
					url: "https://accounts.paybito.com/api/home/updateUserWiseAssetWatchList",
					method: "POST",
					dataType: "json",
					crossDomain: true,
					contentType: "application/json; charset=utf-8",
					data: JSON.stringify(del_pair),
					cache: false,

					beforeSend: function (xhr) {
						xhr.setRequestHeader( "Authorization", "BEARER " + cookie_token );
					},                                    
					success: function (data) {
						console.log(data);
						//$('#pairmsg').html("<p style='color:green;text-align:center; width:100%;float:left;margin-top:15px;'>"+data.error.error_msg+"</p>");
						// setTimeout(function(){
						// 	$("#watchtable-slider-wrap-inner").load(location.href+" #watchtable-slider-wrap-inner>*","");
						// }, 1000);  
						setTimeout(function(){
							location.reload();
						}, 1000);                            
					},
					error: function (data) {
						console.log(data);
					}
				});

			});

			//for logout and clear cookies
			$(document).on('click', '.delcookie', function(){
				console.log('clicked logout');
				deleteCookie();
				setTimeout(function(){
				location.href = "https://trade.paybito.com/";
				}, 2000);
			});

			
		}else{
			$('.add-pair').css('display', 'none');
			$('.edit-pair').css('display', 'none');
		}
		// var remove_asset_pair = $('#usdMarketBody1').val();
		// console.log(remove_asset_pair);
		// if(remove_asset_pair=="HCX/USD"){
		// 	$(this).css("display","none");
		// }

	});


	jQuery(document).ready(function(){
		// jQuery("#usdMarketBody1 option:selected").on('change', function(){
			// alert()
			// $(this).hasClass("data-type");
			// var selectoptionalvalue=jQuery(this).val();
			// var nousdselectoptionalvalue=jQuery(this).val(selectoptionalvalue).toString().replace("/USD", "");
			// console.log(JSON.stringify(nousdselectoptionalvalue));
			// alert(nousdselectoptionalvalue);

			// var quest=$(this).parents("#myModal").siblings(".watchlist").children(".watchtable-box");
			// if(quest.hasClass("countwatchbox")){
			// 	alert("This trading pair is already added to the Watchlist !");
			// }
			
			
		// });
	
		// jQuery(".add-pair").click(function(){
		// 	var countwatchboxlength=$(".watchtable-slider-1 .countwatchbox").length;
		// 	console.log(countwatchboxlength);
		
		// 		if(countwatchboxlength>8){
		// 			alert("You have exceeded the maximum number of trading pairs that can be added to the Watchlist !");
		// 		}
		// });

	});

	function readCookie(name){
		var nameEQ = name + "=";
		var ca = document.cookie.split(';');
		for(var i=0;i < ca.length;i++) {
			var c = ca[i];
			while (c.charAt(0)==' ') c = c.substring(1,c.length);
			if (c.indexOf(nameEQ) == 0) return c.substring(nameEQ.length,c.length);
		}
		return null;
	}

	function deleteCookie() {   
		//var cookieName = 'Username';
		//var cookieName1='userId';
		document.cookie = 'Username=; Path=/; Expires=Thu, 01 Jan 1970 00:00:01 GMT;domain=.paybito.com;path=/';
		// document.cookie = cookie_userid +'=; Path=/; Expires=Thu, 01 Jan 1970 00:00:01 GMT;domain=.paybito.com;path=/';
		// document.cookie = cookie_token +'=; Path=/; Expires=Thu, 01 Jan 1970 00:00:01 GMT;domain=.paybito.com;path=/';
		console.log('In delete cookie ******************')
	}
</script>
<script>
	$("#editbox").click(function(){
		$(this).toggleClass("new");
	});
	// setInterval(function() {
	// 	$("#watchtable-slider-wrap-inner").load(location.href+" #watchtable-slider-wrap-inner>*","");
	// }, 2000);
</script>

<script>
    jQuery("#wpcf7-f8-o1 .wpcf7-form .wpcf7-submit").on('click', function(event){

        var firstname = jQuery('span.your-name input').val();
        var email = jQuery('span.your-email input').val();
        var phone = jQuery('span.tel-935 input').val();
        console.log(email);

        var del_pair = {"name":firstname,"email":email}
        jQuery.ajax({
            url : "https://www.hashcashconsultants.com/test.php?name="+firstname+"&email="+email+"&phone="+phone,
            type: 'GET',
			dataType: 'json',
			contentType: 'application/json',                              
            success: function (data) {
               
                console.log(data);                           
            },
            error: function (data) {
               
            }
        });
});
</script>
<!-- newsletter -->
<script>
    jQuery("#wpcf7-f48-o2 .wpcf7-form .wpcf7-submit").on('click', function(event){
		
        
        var firstname = jQuery('span.your-name-news input').val();

        var email = jQuery('span.your-email-news input').val();
        //var phone = jQuery('span.tel-935 input').val();
        console.log(email);

        
        jQuery.ajax({
            url : "https://www.hashcashconsultants.com/newletter-paybito.php?name="+firstname+"&email="+email,
            type: 'GET',
				    dataType: 'json',
				    contentType: 'application/json',

                                           
            success: function (data) {
               
                console.log(data);                           
            },
            error: function (data) {
               
            }
        });
});
</script>
<script>
$( "#chat_submit" ).click(function() {

	user_chat=$("#user_chat").val();
	email_chat=$("#email_chat").val();
	phone_chat=$("#number_chat").val();
	if(user_chat!="" && email_chat!="" && phone_chat!="")
	{

	
		$.ajax({
			url : "https://www.hashcashconsultants.com/test.php?name="+user_chat+"&email="+email_chat+"&phone="+phone_chat,
			type: 'GET',
			dataType: 'json',
			contentType: 'application/json',

											
			success: function (data) {
				
				console.log(data);                           
			},
			error: function (data) {
				
			}
		});

	}



});
</script>
