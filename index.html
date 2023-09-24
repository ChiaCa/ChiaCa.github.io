<input type="hidden" id="statu" value="">
<input type="hidden" id="stationId" value="">
<input type="hidden" id="search_produceNo" value="">
<input type="hidden" id="search_orderNo" value="">
<input type="hidden" id="search_client" value="">
<input type="hidden" id="search_startDT" value="">
<input type="hidden" id="search_endDT" value="">

<div class="pageTitle"><?php echo lang('lang_pageName'); ?></div><!-- 工單搜尋 -->

<div class="pageBox" id="produce_status">
    <div class="cardTitle yellow" id='searchTitle'><?php echo lang('lang_search'); ?></div><!-- 請輸入搜尋條件 -->
    <div class="cardBox">
        <div class="row">
            <div class="col-1 d-flex align-items-center justify-content-end appLabel w_100px"><?php echo lang('lang_customernumber'); ?></div><!-- 客戶編號 -->
            <form onkeydown="if(event.keyCode==13)return false;">
                <div class="col appInput"><input type="text" id="clientNo" maxlength="50" autocomplete="off" list="client_datalist"></div>
                <datalist id="client_datalist"></datalist>
            </form>
        </div>
        <div class="row">
            <div class="col-1 d-flex align-items-center justify-content-end appLabel w_100px"><?php echo lang('lang_productnumber'); ?></div><!-- 產品編號 -->
            <form onkeydown="if(event.keyCode==13)return false;">
                <div class="col appInput"><input type="text" id="productNo" maxlength="50" autocomplete="off" list="product_datalist"></div>
                <datalist id="product_datalist"></datalist>
            </form>
        </div>
        <div class="btnBox">
            <div class="alertMsg" id="alertMsg_search"></div>
            <button type="button" class="button"           onclick='search_produce();'><?php echo lang('lang_searchbutton'); ?></button><!-- 搜尋 -->
            <button type="button" class="button removeRed" onclick='clean_search();'><?php echo lang('lang_resetbutton'); ?></button><!-- 清除 -->
        </div>
    </div>
</div>

<div class="pageBox" id="produce_status">
    <div class="cardTitle yellow" id='searchTitle'><?php echo lang('lang_produceNo'); ?></div><!-- 工單編號 -->
    <div class="cardBox">
        <div class="row">
            <div class="col-1 d-flex align-items-center justify-content-end appLabel w_100px"><?php echo lang('lang_produceNo'); ?></div><!-- 工單編號 -->
            <form onkeydown="if(event.keyCode==13)return false;">
                <div class="col appInput"><input type="text" id="produceNo" maxlength="50" autocomplete="off" list="produce_datalist"></div>
                <datalist id="produce_datalist"></datalist>
            </form>
        </div>

        <div class="btnBox">
            <div class="alertMsg" id="alertMsg"></div>
            <button type="button" class="button"           onclick='search_list();'><?php echo lang('lang_searchbutton'); ?></button><!-- 搜尋 -->
            <button type="button" class="button removeRed" onclick='clean_produceNo();'><?php echo lang('lang_resetbutton'); ?></button><!-- 清除 -->
        </div>
    </div>
</div>


<div id="produceAll"></div>
<script type="text/javascript" src='<?php echo base_url(); ?>appoint/javascript/common_function.js'></script>
<script type="text/javascript" src='<?php echo base_url(); ?>appoint/javascript/dashboard_app.js'></script>
<script>
    // client_datalist();
    // product_datalist();
    // produce_datalist();
    var baseUrl = document.getElementById('base_url').value;
    $(document).ready(function() {
        $('input[type=radio][name=station]').change(function() {
            var stationId = this.value;
            var hideobj = document.getElementById("produce_status");
            hideobj.style.display = "";
        });
    })

    var statu = document.getElementById("statu").value;
    if (statu) {
        $("input[type=radio][value=" + statu + "]")[0].checked = true;
        produce_list();
    }

    $(document).ready(function() {
        $('input[type=radio][name=produce_statu]').change(function() {
            var statu = this.value;
            produce_list();
        });
    })

    // 工單列表-尚無資料
    function produce_noData() {
        document.getElementById('alertMsg').innerHTML = "<?php echo lang('lang_noproduceNo'); ?>"; //查無工單
    }

    // 繪製NG原因清單_detail用
    function NgreasonListStr_detail(ngreason) {
        var table = "<table class='appSubTable'>";
        table += "<thead><th><?php echo lang('lang_quantity'); ?></th><th><?php echo lang('lang_ngreason'); ?></th><th><?php echo lang('lang_photo'); ?></th></thead>"; //數量 原因 圖片
        ngreason.forEach(function(value, index, array) {
            table += '<tr>';
            table += "<td class='textCenter'>" + value['ngcount'] + "</td>";
            var ngreason = changeLanguage(value['ngreason']); //多國語言切換
            table += "<td>" + ngreason + "</td>";
            table += "<td class='textCenter w_80px'>";
            if (value['img']) {
                var baseUrl = document.getElementById('base_url').value;
                var ngImgPath = document.getElementById('STAFFWORKRECORD_PATH').value;
                value['img'].forEach(function(img) {
                    var ngImg = baseUrl + ngImgPath + img['imgUUIDName'];
                    table += "<div class='appImgBox'><img src='" + ngImg + "' onclick='openImg(" + '"' + ngImg + '"' + ")'></div>";
                });
            }
            table += '</td></tr>';

        });
        table += '</table>';
        return table;
    }

    // 列表-依序列出所有工單
    function produce_data(data, data_obj) {
        console.log(data);
        var baseUrl = document.getElementById('base_url').value;
        var tab_phone = "";
        var qcdata = "";
        var staffworkrecorddata = "";

        //--- 工單基本資料 ---//
        tab_phone += '<div class="pageBox">';
        tab_phone += '<div class="cardTitle" onclick="look_slideToggle(' + "'producePhone'" + ')"><?php echo lang('lang_produceData'); ?></div>'; //工單基本資料
        tab_phone += '<div class="cardBox producePhone" id="producePhone">';
        tab_phone += '<div class="row">';

        tab_phone += '<div class="col-lg-6 col-xl-4">';
        var pNewQuantity = data[0]['pNewQuantity']; //現場數量
        var produceQuantity = data[0]['quantity']; //工單數量
        var produceUnit = data[0]['unit']; //工單數量單位
        var coatingName = data[0]['coatingName']; //鍍膜材料

        //是否急單
        var isRush = "<?php echo lang('lang_no'); ?>"; //否
        if (data[0]['isRush'] == 1) {
            var rushDate = "";
            if (data[0]['rushDate']) {
                rushDate = data[0]['rushDate'];
            }
            isRush = "<span class='redText'><?php echo lang('lang_yes'); ?>(" + rushDate + ")</span>"; //是
        }

        //鍍膜顏色&編號
        var colorName = '-';
        var colorNo = '-';
        if (data[0]['colorName']) {
            colorName = data[0]['colorName'];
        }
        if (data[0]['colorNo']) {
            colorNo = data[0]['colorNo'];
        }

        var produceNo = data[0]['produceNo']; //工單編號
        if (data[0]['reworkNo']) {
            produceNo = data[0]['reworkNo'];
            tab_phone += "<div class='appLabel'><?php echo lang('lang_reworkNo'); ?>：</div>"; //重工單編號
        } else {
            tab_phone += "<div class='appLabel'><?php echo lang('lang_produceNo'); ?>：</div>"; //工單編號
        }
        tab_phone += "<span>" + produceNo + "</span>";
        tab_phone += "</div>";

        tab_phone += '<div class="col-lg-6 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_createTime'); ?>：</div>"; //建立時間
        tab_phone += "<span>" + data[0]['createTime'] + "</span>";
        tab_phone += "</div>";

        tab_phone += '<div class="col-lg-6 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_customernumber'); ?>：</div>"; //客戶名稱[編號]
        tab_phone += "<span>" + data[0]['company'] + "[" + data[0]['clientNo'] + "]" + "</span>";
        tab_phone += "</div>";

        tab_phone += '<div class="col-lg-12 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_productnumber'); ?>：</div>"; //產品名稱[編號]
        tab_phone += "<span>" + data[0]['name'] + "[" + data[0]['itemNo'] + "]" + "</span>";
        tab_phone += "</div>";
        var orderDetail_img = '-';
        if (data[0]['img']) {
            var baseUrl = document.getElementById('base_url').value;
            var imgPath = document.getElementById('PRODUCT_PATH').value;
            var img_data = JSON.parse(data[0]['img']);
            if (img_data.length > 0) {
                orderDetail_img='';
                for (var j = 0; j < img_data.length; j++) {
                    var orderImg = baseUrl + imgPath + img_data[j];
                    orderDetail_img += "<div class='appImgBox'><img src='" + orderImg + "' onclick='openImg(" + '"' + orderImg + '"' + ")'></div>";
                }
            }
        }

        tab_phone += '<div class="col-lg-12 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_productphoto'); ?>：</div>"; //產品圖片
        tab_phone += "<span>" + orderDetail_img + "</span>";
        tab_phone += "</div>";

        tab_phone += '<div class="col-lg-6 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_colornumber'); ?>：</div>"; //顏色[編號]
        tab_phone += "<span>" + colorName + "[" + colorNo + "]" + "</span>";
        tab_phone += "</div>";

        tab_phone += '<div class="col-lg-6 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_produceQuantity'); ?>：</div>"; //加工數量
        tab_phone += "<span>" + produceQuantity + produceUnit + "</span>";
        tab_phone += "</div>";

        var displayClass = '';
        //如果工單數量跟修改後工單數量一樣，就不顯示
        if(produceQuantity==pNewQuantity){
            displayClass='none';
        }
        tab_phone += '<div class="col-lg-6 col-xl-4 '+displayClass+'">';
        tab_phone += "<div class='appLabel'>調整後之工單數量：</div>"; //現場數量
        tab_phone += "<span>" + pNewQuantity + produceUnit + "</span>";
        tab_phone += "</div>";

        tab_phone += '<div class="col-lg-6 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_coatingName'); ?>：</div>"; //鍍膜材料
        tab_phone += "<span>" + coatingName + "</span>";
        tab_phone += "</div>";

        tab_phone += '<div class="col-lg-6 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_isrush'); ?>：</div>"; //是否急單
        tab_phone += "<span>" + isRush + "</span>";
        tab_phone += "</div>";

        tab_phone += '<div class="col-lg-6 col-xl-4">';
        tab_phone += "<div class='appLabel'><?php echo lang('lang_deliverydate'); ?>：</div>"; //交期
        tab_phone += "<span>" + data[0]['ECDate'] + "</span>";
        tab_phone += "</div>";

        //工單已完成
        if (data[0]['completeDate']) {
            tab_phone += '<div class="col-lg-6 col-xl-4">';
            tab_phone += "<div class='appLabel'><?php echo lang('lang_completedate'); ?>：</div>"; //完成日期
            tab_phone += "<span>" + data[0]['completeDate'] + "</span>";
            tab_phone += "</div>";
        } else {
            tab_phone += '<div class="col-lg-12 col-xl-4">';
            tab_phone += "<div class='appLabel'><?php echo lang('lang_nowworkstation'); ?>/<?php echo lang('lang_process'); ?>：</div>"; //目前工作站 / 製程
            tab_phone += "<span>";
            if (data['now_working_station'] == "無進站資料") {
                var workstationName = changeLanguage(data['produce_process'][0]['workstationName']); //多國語言切換
                var processName = changeLanguage(data['produce_process'][0]['processName']); //多國語言切換
                tab_phone += "<?php echo lang('lang_noentryworkstation'); ?>(<?php echo lang('lang_firstworkstation'); ?>:" + workstationName + "/" + processName + ")"; // 無進站資料 //第一站為
            } else if (data['now_working_station'] == "委外中") {
                tab_phone += "<?php echo lang('lang_osing'); ?>"; //委外中
            } else if (data['now_working_station'] == "尚未建立委外單") {
                tab_phone += "<?php echo lang('lang_nocreateos'); ?>"; //尚未建立委外單
            } else {
                var isComplete = "<?php echo lang('lang_notyetoutbound'); ?>"; //尚未出站
                if (data['is_complete'].length > 0) {
                    if (data['is_complete'][0]['CompleteQuantity'] > 0) {
                        isComplete = "<?php echo lang('lang_hasoutstationrecord'); ?>"; //已有出站紀錄
                    }
                }
                if (data['now_working_station']['module'] == 3) { //委外製程
                    isComplete = "<?php echo lang('lang_outsourcedcompletionrecord'); ?>"; //已有委外完成紀錄
                }
                var workstationName = changeLanguage(data['now_working_station']['workstationName']); //多國語言切換
                var processName = changeLanguage(data['now_working_station']['processName']); //多國語言切換
                tab_phone += workstationName + "/" + processName + " (" + isComplete + ")";
            }
            tab_phone += "</span></div>";

            tab_phone += '<div class="col-lg-12 col-xl-4">';
            tab_phone += "<div class='appLabel'><?php echo lang('lang_nextworkstation'); ?>/<?php echo lang('lang_process'); ?>：</div>"; //下一個工作站 / 製程
            tab_phone += "<span>";
            if (data['now_working_station'] == "無進站資料") {
                tab_phone += "<?php echo lang('lang_noentryworkstation'); ?>"; //無進站資料
            } else {
                var workstationName = changeLanguage(data['next_work_station']['workstationName']); //多國語言切換
                var processName = changeLanguage(data['next_work_station']['processName']); //多國語言切換
                tab_phone += "" + workstationName + "/" + processName;
            }
            tab_phone += "</span></div>";
        }
        tab_phone += '</div></div></div>';

        //--- 各站數量資料 ---//
        var workrecordlist = data['workrecordlist'];
        tab_phone += '<div class="pageBox">';
        tab_phone += '<div class="cardTitle" onclick="look_slideToggle(' + "'stationrecordlist'" + ')"><?php echo lang('lang_numberofstations'); ?></div>'; //工作站狀況
        tab_phone += '<div class="cardBox stationrecordlist" id="stationrecordlist">';
        if (workrecordlist.length > 0) {
            var workrecordUnit = workrecordlist[0]['unit'];
            tab_phone += "<div><?php echo lang('lang_stationquaunit'); ?>：" + workrecordUnit + "</div>"; //進出站數量單位
            tab_phone += "<table class='appTable'>";
            tab_phone += "<thead>"; //工作站 製程 站內數量 已出站數量 退回數量(隱藏) 紀錄時間
            tab_phone += "<th><?php echo lang('lang_workstation'); ?></th><th><?php echo lang('lang_process'); ?></th><th><?php echo lang('lang_quantityinproduction'); ?></th><th><?php echo lang('lang_amountcompleted'); ?></th><th class='inlineNone'><?php echo lang('lang_returnquantity'); ?></th><th><?php echo lang('lang_recordtime'); ?></th>";
            tab_phone += "</thead>";
            var ppNo = 0;
            data['produce_process'].forEach(function(value, index, array) {
                ppNo++;
                let quantity = 0;
                let completequantity = 0;
                let recordTime = '<?php echo lang('lang_notyetinthisworkstation'); ?>'; //尚未進入此站
                let return_count = 0;

                //在製數量&完成數量&紀錄時間
                if (value['makingInformation']) {
                    if (value['makingInformation'].length > 0) {
                        temp_data = value['makingInformation'][0];
                        quantity = temp_data['quantity'];
                        completequantity = temp_data['completeQuantity'];
                        recordTime = temp_data['recordTime'];
                    }
                }

                //退回數量
                if (value['returnInformation']) {
                    if (value['returnInformation'].length > 0) {
                        value['returnInformation'].forEach(function(returnvalue, returnindex, returnarray) {
                            return_count += parseFloat(returnvalue['quantity']);
                        });
                    }
                }

                //製程若在同一工作站時則不顯示工作站名稱及數量資訊
                var workstationName = changeLanguage(value['workstationName']); //多國語言切換
                var processName = changeLanguage(value['processName']); //多國語言切換
                if (ppNo != 1) {
                    if (array[index]['stationId'] == array[index - 1]['stationId']) {
                        tab_phone += "<tr><td></td><td>" + value['processName'] + "</td><td colspan='4'></td></tr>";
                    } else {
                        tab_phone += "<tr><td>" + workstationName + "</td><td>" + processName + "</td><td class='textCenter'>" + quantity + "</td><td class='textCenter'>" + completequantity + "</td><td class='textCenter inlineNone'>" + return_count + "</td><td>" + recordTime + "</td></tr>";
                    }
                } else {
                    tab_phone += "<tr><td>" + workstationName + "</td><td>" + processName + "</td><td class='textCenter'>" + quantity + "</td><td class='textCenter'>" + completequantity + "</td><td class='textCenter inlineNone'>" + return_count + "</td><td>" + recordTime + "</td></tr>";
                }

                //QC資料整理
                if (value['qcrecord']) {
                    if (value['qcrecord'].length > 0) {
                        var totalNg = 0,
                            totalPass = 0;
                        value['qcrecord'].forEach(function(qcrecordvalue, qcrecordindex, qcrecordarray) {
                            //總OK數量
                            if (qcrecordvalue['pass'].length > 0) {
                                totalPass += parseFloat(qcrecordvalue['pass']);
                            }

                            //總NG數量
                            var ng_array = JSON.parse(qcrecordvalue['ngReason']);
                            if (ng_array.length > 0) {
                                ng_array.forEach(function(ngarrayvalue, ngarrayindex, ngarrayarray) {
                                    totalNg += parseFloat(ngarrayvalue['ngcount']);
                                });
                            }
                        });

                        var workstationName = changeLanguage(value['workstationName']); //多國語言切換
                        var processName = changeLanguage(value['processName']); //多國語言切換
                        qcdata += "<tr><td>" + workstationName + "</td><td>" + processName + "</td>";
                        qcdata += "<td><div class='inlineBlock'><div class='appLabel'><?php echo lang('lang_totalOkcount'); ?>：</div>" + totalPass + produceUnit + "　</div>"; //總OK數
                        qcdata += "<div class='inlineBlock'><div class='appLabel'><?php echo lang('lang_totalngcount'); ?>：</div>" + totalNg + produceUnit + '</div>'; //總NG數
                        qcdata += '<div><div class="cardSubTitle" onclick="look_slideToggle(' + "'qcDetailList" + value['processId'] + "'" + ')"><?php echo lang('lang_qcDetail'); ?><i class="fa-solid fa-angle-down"></i></div></div>'; //品檢詳細紀錄
                        qcdata += '<div class="qcDetailList' + value['processId'] + '" id="qcDetailList' + value['processId'] + '" style="display:none;">';

                        //品檢詳細紀錄
                        var qcDetailno = 0;
                        value['qcrecord'].forEach(function(qcrecordvalue, qcrecordindex, qcrecordarray) {
                            qcDetailno++;
                            qcdata += '<div class="cardSubBox">';
                            qcdata += '<div class="cardThreeTitle"><?php echo lang('lang_qc'); ?>-' + qcDetailno + '</div>';
                            //OK數
                            qcdata += '<div><div class="appLabel"><?php echo lang('lang_okcount'); ?>：</div>' + qcrecordvalue['pass'] + produceUnit + '</div>'; //OK數

                            //NO數&原因
                            var ng_array = JSON.parse(qcrecordvalue['ngReason']);
                            var ngDetail = '',
                                ngNo = 0,
                                subTotalNg = 0;
                            if (ng_array.length > 0) {
                                ngDetail += '<table class="appSubTable">';
                                ngDetail += '<thead><th><?php echo lang('lang_ngcount'); ?></th><th><?php echo lang('lang_ngreason'); ?></th><th><?php echo lang('lang_photo'); ?></th></thead>'; //NG數 NG原因 參考照片
                                ng_array.forEach(function(ngarrayvalue, ngarrayindex, ngarrayarray) {
                                    subTotalNg += parseFloat(ngarrayvalue['ngcount']); //NG數量小計
                                    ngarrayvalue['ngreason'] = ngarrayvalue['ngreason'].replace(',', '、');
                                    ngDetail += '<tr>';
                                    ngDetail += "<td class='textCenter w_50px'>" + ngarrayvalue['ngcount'] + "</td>";
                                    var ngreason = changeLanguage(ngarrayvalue['ngreason']); //多國語言切換
                                    ngDetail += "<td>" + ngreason + "</td>";
                                    ngDetail += "<td class='textCenter w_80px'>";
                                    if (ngarrayvalue['img']) {
                                        var ngImgPath = document.getElementById('STAFFWORKRECORD_PATH').value;
                                        ngarrayvalue['img'].forEach(function(img) {
                                            var ngImg = baseUrl + ngImgPath + img['imgUUIDName'];
                                            ngDetail += "<div class='appImgBox'><img src='" + ngImg + "' onclick='openImg(" + '"' + ngImg + '"' + ")'></div>";
                                        });
                                    }
                                    ngDetail += '</td></tr>';
                                });
                                ngDetail += '</table>';
                            }

                            //品檢人員
                            var staffArr = [];
                            qcrecordvalue['staffdata'].forEach(function(staffvalue, staffindex, staffarray) {
                                var staff = staffvalue[0]['name'] + "[" + staffvalue[0]['staffNo'] + "]";
                                staffArr.push(staff);
                            });
                            var staffStr = staffArr.join('、');
                            
                            qcdata += '<div><div class="appLabel"><?php echo lang('lang_ngcount'); ?>：</div>' + subTotalNg + produceUnit + '</div>'; //NG數
                            qcdata += '<div><div class="appLabel"><?php echo lang('lang_basketcount'); ?></div>' + qcrecordvalue['basketCount'] + '</div>'; //籃數
                            qcdata += '<div>' + ngDetail + '</div>';
                            qcdata += '<div><div class="appLabel"><?php echo lang('lang_qcSaffno'); ?>：</div>' + staffStr + '</div>'; //品檢人員
                            if (qcrecordvalue['remark']) {
                                qcdata += '<div><div class="appLabel"><?php echo lang('lang_remark'); ?>：</div>' + qcrecordvalue['remark'] + '</div>'; //備註
                            }
                            qcdata += '<div><div class="appLabel"><?php echo lang('lang_recordtime'); ?>：</div>' + qcrecordvalue['createTime'] + '</div>'; //紀錄時間
                            qcdata += '</div>';
                        });
                        qcdata += '</div>';
                        qcdata += '</td></tr>';
                    }
                }

                //報工紀錄
                if (value['staffworkrecord']) {
                    if (value['staffworkrecord'].length > 0) {
                        var recordCount = value['staffworkrecord'].length;
                        var workstationName = changeLanguage(value['workstationName']); //多國語言切換
                        var processName = changeLanguage(value['processName']); //多國語言切換
                        staffworkrecorddata += "<tr><td rowspan='" + recordCount + "'>" + workstationName + "</td><td rowspan='" + recordCount + "'>" + processName + "</td>";
                        value['staffworkrecord'].forEach(function(staffworkrecordvalue, staffworkrecordindex, staffworkrecordarray) {
                            if (staffworkrecordvalue['endTime']) {
                                var endTime = staffworkrecordvalue['endTime'];
                            } else {
                                var endTime = "<?php echo lang('lang_notfinishedwork'); ?>"; //尚未結束報工
                            }
                            staffworkrecorddata += "<td class='fontSize_08rem'>" + staffworkrecordvalue['name'] + "[" + staffworkrecordvalue['staffNo'] + "]" + "</td><td class='fontSize_08rem'>" + staffworkrecordvalue['startTime'] + "</td><td class='fontSize_08rem'>" + endTime + "</td></tr>";
                        });
                    }
                }
            });
            tab_phone += "</table>";
        } else {
            tab_phone += "<div class='alertMsg'><?php echo lang('lang_noentryworkstation'); ?></div>"; //無進站資料
            $("#produceAll").html(tab_phone);
            return;
        }

        //--- 工單進出站資料---//
        tab_phone += '<div class="cardSubTitle" onclick="look_slideToggle(' + "'workrecordlist'" + ')"><?php echo lang('lang_inout'); ?><i class="fa-solid fa-angle-down"></i></div>'; //進出站詳細資料
        tab_phone += '<div class="cardBox workrecordlist" id="workrecordlist" style="display:none;">';
        tab_phone += "<table class='appTable'>";
        tab_phone += "<thead>";
        tab_phone += "<th>No</th><th><?php echo lang('lang_workstation'); ?></th><th><?php echo lang('lang_worktype'); ?></th><th><?php echo lang('lang_quantity'); ?></th><th><?php echo lang('lang_staffno'); ?></th>"; //工作站 作業類別 數量 人員[編號]
        tab_phone += "</thead>";
        //列出工單進出站狀況
        workrecordlist.forEach(function(value, index, array) {
            var no = index + 1;
            if (value['workClass'] == 0) {
                value['workClass'] = "<?php echo lang('lang_in'); ?>"; //進站
            } else if (value['workClass'] == 1) {
                value['workClass'] = "<?php echo lang('lang_out'); ?>"; //出站
            } else if (value['workClass'] == 2) {
                if (value['class'] == 1) {
                    value['workClass'] = "<?php echo lang('lang_returnto'); ?>"; //退回
                } else {
                    value['workClass'] = "<?php echo lang('lang_returnfrom'); ?>"; //被退回
                }
            } else {
                value['workClass'] = "<?php echo lang('lang_change'); ?>"; //異動
            }

            if (value['class'] == 0) {
                quantity = "+" + value['quantity'];
            } else {
                quantity = "-" + value['quantity'];
            }

            var workstationName = changeLanguage(value['workstationName']); //多國語言切換
            tab_phone += "<tr><td rowspan='2' class='textCenter w_30px'>" + no + "</td><td>" + workstationName + "</td><td class='textCenter w_100px'>" + value['workClass'] + "</td><td class='textCenter w_100px'>" + quantity + "</td><td>" + value['staffName'] + "[" + value['staffNo'] + "]</td></tr>";
            tab_phone += "<tr><td colspan='4'><div><div class='appLabel'><?php echo lang('lang_recordtime'); ?>：</div>" + value['recordTime'] + "</div>"; //紀錄時間
            var remark = '';
            if (value['remark']) {
                remark = value['remark'];
                tab_phone += "<div><div class='appLabel'><?php echo lang('lang_remark'); ?>：</div>" + remark + "</div>"; //備註
            }
            tab_phone += "</td></tr>";
        });
        tab_phone += '</table>';
        tab_phone += '</div>';
        tab_phone += '</div></div>';

        //品檢資料
        if (qcdata.length > 0) {
            tab_phone += '<div class="pageBox">';
            tab_phone += '<div class="cardTitle" onclick="look_slideToggle(' + "'qcrecordlist'" + ')"><?php echo lang('lang_qc'); ?></div>'; //品檢資料
            tab_phone += '<div class="cardBox qcrecordlist" id="qcrecordlist">';
            tab_phone += "<table class='appTable'>";
            tab_phone += "<thead><th><?php echo lang('lang_workstation'); ?></th><th><?php echo lang('lang_process'); ?></th><th><?php echo lang('lang_result'); ?></th></thead>"; //工作站 製程 品檢結果
            tab_phone += qcdata;
            tab_phone += '</table>';
            tab_phone += '</div></div>';
        }

        //報工資料
        if (staffworkrecorddata.length > 0) {
            tab_phone += '<div class="pageBox">';
            tab_phone += '<div class="cardTitle" onclick="look_slideToggle(' + "'staffrecordlist'" + ')"><?php echo lang('lang_staffwork'); ?></div>'; //報工資料
            tab_phone += '<div class="cardBox staffrecordlist" id="staffrecordlist">';
            tab_phone += "<table class='appTable'>";
            tab_phone += "<thead><th><?php echo lang('lang_workstation'); ?></th><th><?php echo lang('lang_process'); ?></th><th><?php echo lang('lang_staffno'); ?></th><th><?php echo lang('lang_starttime'); ?></th><th><?php echo lang('lang_endtime'); ?></th></thead>"; //工作站 製程 人員[編號] 開始時間 結束時間
            tab_phone += staffworkrecorddata;
            tab_phone += '</table>';
            tab_phone += '</div></div>';
        }

        //鍍膜資料
        if (data['coatingrecord'].length > 0) {
            var coatingrecorddata = "";
            data['coatingrecord'].forEach(function(coatingrecordvalue, coatingrecordindex, coatingrecordarray) {
                coatingrecorddata += "<tr><td>" + coatingrecordvalue['macRecordNo'] + "</td><td>" + coatingrecordvalue['name'] + "[" + coatingrecordvalue['mNo'] + "]" + "</td>";
                coatingrecorddata += "<td><div><div class='appLabel'><?php echo lang('lang_coatingquantity'); ?>：</div>" + coatingrecordvalue['quantity'] + produceUnit + "　</div>"; //鍍膜數量
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_starttime'); ?>：</div>" + coatingrecordvalue['startTime'] + '</div>'; //鍍膜開始時間
                var endTime = "<?php echo lang('lang_coatingnotyet'); ?>"; //鍍膜尚未結束
                if (coatingrecordvalue['endTime']) {
                    endTime = coatingrecordvalue['endTime'];
                }
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_endtime'); ?>：</div>" + endTime + '</div>'; //鍍膜結束時間
                coatingrecorddata += '<div><div class="cardSubTitle" onclick="look_slideToggle(' + "'coatingrecordList" + coatingrecordvalue['macRecordNo'] + "'" + ')"><?php echo lang('lang_readmore'); ?><i class="fa-solid fa-angle-down"></i></div></div>'; //更多詳細資料
                coatingrecorddata += '<div class="coatingrecordList' + coatingrecordvalue['macRecordNo'] + '" id="coatingrecordList' + coatingrecordvalue['macRecordNo'] + '" style="display:none;">';
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_operating'); ?>：</div>" + JSON.parse(coatingrecordvalue['color']) + "</div>"; //操作條件
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_coating'); ?>：</div>" + JSON.parse(coatingrecordvalue['coating']) + "</div>"; //材質
                var stafflist = "";
                coatingrecordvalue['stafflist'].forEach(function(staffvalue, staffindex, staffarray) {
                    if (staffindex != coatingrecordvalue['stafflist'].length - 1) {
                        stafflist += staffvalue[0]['name'] + "[" + staffvalue[0]['staffNo'] + "]、";
                    } else {
                        stafflist += staffvalue[0]['name'] + "[" + staffvalue[0]['staffNo'] + "]";
                    }
                });
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_staffno'); ?>：</div>" + stafflist + "</div>"; //操作人員
                var view = "-",
                    result = "-";
                if (coatingrecordvalue['endTime']) {
                    if (coatingrecordvalue['view'] == 1) {
                        view = "<?php echo lang('lang_no'); ?>"; //否
                    } else {
                        view = "<?php echo lang('lang_yes'); ?>"; //是
                    }
                    if (coatingrecordvalue['result'] == 1) {
                        result = "NG";
                    } else {
                        result = "OK";
                    }
                }
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_view'); ?>：</div>" + view + "</div>"; //是否目視
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_result'); ?>：</div>" + result + "</div>"; //品檢結果
                var ngtab = "-",
                    ngreason;
                if (coatingrecordvalue['reason']) {
                    ngreason = (JSON.parse(coatingrecordvalue['reason']));
                    if (ngreason.length > 0) {
                        ngtab = NgreasonListStr_detail(ngreason);
                    }
                }
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_ngreason'); ?>：</div>" + ngtab + "</div>"; //不良原因
                var lab = coatingrecordvalue['labValueL'] + '*' + coatingrecordvalue['labValueA'] + '*' + coatingrecordvalue['labValueB'];
                coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_labvalue'); ?>：</div>" + lab + "</div>"; //L*A*B值
                if (coatingrecordvalue['remark']) {
                    coatingrecorddata += "<div><div class='appLabel'><?php echo lang('lang_remark'); ?>：</div>" + coatingrecordvalue['remark'] + "</div>"; //備註
                }
                coatingrecorddata += "</div></td><tr>";
            });
            tab_phone += '<div class="pageBox">';
            tab_phone += '<div class="cardTitle" onclick="look_slideToggle(' + "'coatingrecord'" + ')"><?php echo lang('lang_coatingdata'); ?></div>'; //鍍膜資料
            tab_phone += '<div class="cardBox coatingrecord" id="coatingrecord">';
            tab_phone += "<table class='appTable'>";
            tab_phone += "<thead><th><?php echo lang('lang_machinecoatingnumber'); ?></th><th><?php echo lang('lang_machinenumber'); ?></th><th><?php echo lang('lang_coatingdetaildata'); ?></th></thead>"; //鍍膜紀錄編號 機台[編號] 鍍膜詳細資料
            tab_phone += coatingrecorddata;
            tab_phone += '</table>';
            tab_phone += '</div></div>';
        }

        $("#produceAll").html(tab_phone);
    }

    //工單列表-搜尋
    function search_list() {
        var produceNo = document.getElementById('produceNo').value;
        document.getElementById('search_produceNo').value = produceNo;
        document.getElementById('alertMsg').innerHTML = "";
        //欄位檢查
        if (produceNo.length == 0) {
            document.getElementById("alertMsg").innerHTML = "<?php echo lang('lang_pleaseenterproduce'); ?>"; //請輸入工單編號
            return;
        }
        produce_list();
    }
</script>