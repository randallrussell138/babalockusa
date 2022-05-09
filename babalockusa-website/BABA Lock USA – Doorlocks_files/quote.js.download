jQuery(document).ready(
    function($) {

        $(window).on('load', function() {
            var input_value = $("input[name=quantity]").val();
            $("input[name=product_quantity]").val(input_value);
          //  alert(input_value);
        });

        $(".single_variation_wrap .variation_id").change(function() {
        	var var_id = $(this).val();
        	$("._add_to_quote .variation_id").val(var_id);
        });

            
        $('input[name=quantity]').change(function() {
            var input_value = $("input[name=quantity]").val();
        	//alert(input_value);
           $('input[name=product_quantity]').val(input_value);
        });
        $('.product-remove').click(function(){
        	jQuery('.shop_table.cart').css('opacity',0.5);
            setTimeout(function() {
                window.location.reload();
            }, 3000);
        });
       $(document).on('change','.variations select,.variations-table select,.variation_form_section #color,.variation_form_section #pa_color', function() {
            setTimeout(function() { _display_hide() } ,500);
            function _display_hide() {
				var attr = $('.single_variation_wrap').find('.single_add_to_cart_button').attr('disabled');
				if($('.single_variation_wrap').css('display') == 'block' && (typeof attr === typeof undefined || attr === false)) {
                    $('#_add_to_quote_form_wrapper').find('._add_to_quote_submit').removeClass('_hide');
                }
                else if($('.single_variation_wrap').css('display') == 'none' || (typeof attr !== typeof undefined || attr !== false)) {
                    $('#_add_to_quote_form_wrapper').find('._add_to_quote_submit').addClass('_hide');
                }
            }
        });
		_remove_th_on_responsive();
		change_size();
		$(window).resize(
			function() {
				_remove_th_on_responsive();
				change_size();
			}
		);
		
		function _remove_th_on_responsive() {
			if($(window).width() <= 768){
				$('.quote table thead th.product-remove').text(' ');
				$('.quote table thead th.product-thumbnail').text(' ');
			}
			else {
				$('.quote table thead th.product-remove').text('Remove');
				$('.quote table thead th.product-thumbnail').text('Product Image');
			}
		}

		$('#_email_quote_trigger').click(
			function() {
				$('#_send_quote_email_')[0].click();
			}
		);

		$('#send_trigger').click(
			function() {
				var $toSend = $('#_to_send_email').val();
				$('._to_send_email').val($toSend);
				$('.quote_data_wrapper ._submit').click();
			}
		);

		$('#waqt_user_quote_detail').find('._tab_menu_option').click(
			function() {

				$(this).parents('._table_content_wrapper').siblings().find('._tab_accordian_panel').removeClass('active');
				$(this).parents('._table_content_wrapper').siblings().find('._tab_accordian_panel').slideUp();
				if($(this).parents('._table_content_wrapper').find('._tab_accordian_panel').hasClass('active')) {
					$(this).parents('._table_content_wrapper').find('._tab_accordian_panel').removeClass('active');
					$(this).parents('._table_content_wrapper').find('._tab_accordian_panel').slideUp();
				}
				else {
					$(this).parents('._table_content_wrapper').find('._tab_accordian_panel').addClass('active');
					$(this).parents('._table_content_wrapper').find('._tab_accordian_panel').slideDown();
				}
			}
		);

		function change_size(){
			var $target = $('._quoteall_buttons_wrapper');
			var $buttons_wrapper_width = $target.width();
			var $window_width = $(window).width();

			if($buttons_wrapper_width < 550 && $window_width < 950){
				$target.addClass('small_width');
			}
			else if($buttons_wrapper_width > 550 && $window_width > 950) {
				$target.removeClass('small_width');
			}
		}
    }
);

function setCookie(cname, cvalue, exdays) {
    var d = new Date();
    d.setTime(d.getTime() + (exdays * 24 * 60 * 60 * 1000));
    var expires = "expires="+d.toUTCString();
    document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
}

function getCookie(cname) {
    var name = cname + "=";
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
}
