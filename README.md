<?php
header("Content-Type: text/html; charset=UTF-8");
?>
<script src="http://t1.daumcdn.net/mapjsapi/bundle/postcode/prod/postcode.v2.js"></script>
<script>
    new daum.Postcode({
        oncomplete: function(data) {
            if(data.userSelectedType=="R"){

                window.Leaf.getAddress(data.zonecode, data.roadAddress, data.buildingName);
            }
            else{
                window.Leaf.getAddress(data.zonecode, data.jibunAddress, data.buildingName);
            }      
        }
    }).open();
</script>
