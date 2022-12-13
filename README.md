# e2b-converter
English to Bangla or Others converter using php function
<pre>
<code language="php">
if(!function_exists('custom_date')){
		function custom_date(){       
			$months = array("Jan" => "يناير", "Feb" => "فبراير", "Mar" => "مارس", "Apr" => "أبريل", "May" => "مايو", "Jun" => "يونيو", "Jul" => "يوليو", "Aug" => "أغسطس", "Sep" => "سبتمبر", "Oct" => "أكتوبر", "Nov" => "نوفمبر", "Dec" => "ديسمبر");
			    $your_date = date('y-m-d'); // The Current Date
			    $en_month = date("M", strtotime($your_date));
			    foreach ($months as $en => $ar) {
			    	if ($en == $en_month) { $ar_month = $ar; }
			    }

			    $find = array ("Sat", "Sun", "Mon", "Tue", "Wed" , "Thu", "Fri");
			    $replace = array ("السبت", "الأحد", "الإثنين", "الثلاثاء", "الأربعاء", "الخميس", "الجمعة");
			    $ar_day_format = date('D'); // The Current Day
			    $ar_day = str_replace($find, $replace, $ar_day_format);

			    header('Content-Type: text/html; charset=utf-8');
			    $standard = array("0","1","2","3","4","5","6","7","8","9");
			    $eastern_arabic_symbols = array("٠","١","٢","٣","٤","٥","٦","٧","٨","٩");
			    $current_date = $ar_day.' '.date('d').' / '.$ar_month.' / '.date('Y');
			    $arabic_date = str_replace($standard , $eastern_arabic_symbols , $current_date);

			    return $arabic_date;

			}
		}



	if (!function_exists('e2b')) {

	    function e2b($number){        
	        $ci = get_instance();
	        $bn = ["১", "২", "৩", "৪", "৫", "৬", "৭", "৮", "৯", "০"];
    		$en = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "0"];
    		return str_replace($en,$bn, $number);
		}	
	}


	if (!function_exists('e2b')) {

	    function e2b($string){        
	        $ci = get_instance();
	        $search_array= array("১", "২", "৩", "৪", "৫", "৬", "৭", "৮", "৯", "০", "জানুয়ারী", "ফেব্রুয়ারী", "মার্চ", "এপ্রিল", "মে", "জুন", "জুলাই", "আগষ্ট", "সেপ্টেম্বার", "অক্টোবার", "নভেম্বার", "ডিসেম্বার", ":", ",","সকাল ","বিকাল");
    		$replace_array = array("1", "2", "3", "4", "5", "6", "7", "8", "9", "0", "Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec", ":", ",","am","pm"); 

    	// $replace_array= array("1", "2", "3", "4", "5", "6", "7", "8", "9", "0", "January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December", ":", ",");

    	$en_number = str_replace($replace_array,$search_array,$string);   
    	return $en_number;
		}	
	}

</code>
</pre>
