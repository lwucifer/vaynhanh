<template>
    <div class="body">
        <div class="kdlc_mobile_wraper container">
            <div class="row">
                <div class="help col-6" id="wxin">
                    <a title="Vay tiền nhanh Vay nhanh" target="_blank" href="https://www.facebook.com/vaynhanh.tc">
                        <img src="../../../static/img/support/help-fb.png" class="img-responsive support-icon">
                        <span>Hỗ trợ qua Facebook</span>
                    </a>
                </div>
                <div class=" help col-6" id="help_zalo">
                    <a title="Vay tiền nhanh Vay nhanh" target="_blank" href="https://zalo.me/1903420042896326050">
                        <img src="../../../static/img/support/help-zl.png" class="img-responsive support-icon">
                        <span>Hỗ trợ qua Zalo</span>
                    </a>
                </div>
            </div>
            <div class="row">
                <div class="help col-6">
                    <a href="tel: 0247.302.6889">
                        <img src="../../../static/img/support/help-sdt.png" class="img-responsive support-icon">
                        <span>Hỗ trợ qua điện thoại</span>
                    </a>
                </div>
                <div class="help col-6">
                    <a href="https://m.me/vaynhanh.tc" rel="noopener noreferrer" target="_blank">
                        <img src="../../../static/img/support/messenger1.png" class="img-responsive support-icon">
                        <span>Hỗ trợ qua Messenger</span>
                    </a>
                </div>
            </div>
            <div id="question_wraper">
                <div>
                    <h3 class="em_1 _cursor" @tap="active = active === 99 ? 0 : 99" :class="active === 99 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center"> Vay tiền online là gì?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>Vay tiền online giờ là một loại hình xin vay tiền với thủ tục đặc biệt đơn giản chỉ thông qua App trên di động, xác thực thông tin chỉ trong 3 phút. Sau khi thông qua xét duyệt, chỉ 10 phút tiền vào tài khoản. Thao tác đơn giản, phsi dịch vụ thấp.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 1 ? 0 : 1" :class="active === 1 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Quy trình vay tiền như thế nào?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>(1) Tải App và tiến hành đăng ký/đăng nhập</p>
                        <p>(2) Điền các thông tin liên quan và đợi xét duyệt</p>
                        <p>(3) Sau khi thông qua xét duyệt, lúc này bạn cần chờ giải ngân là xong.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 2 ? 0 : 2" :class="active === 2 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Vay tiền cần có những thông tin nào?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p> Bạn chỉ cần 3 phút hoàn thành thông tin trên điện thoại: Bạn cần điền chính xác thông tin cá nhân của bạn (Chụp ảnh cá nhân cần chụp rõ khuôn mặt bạn, thông tin CMT cần rõ ràng, không bị tẩy xóa), thông tin người liên hệ, thông tin công việc và một số thông tin liên quan.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 3 ? 0 : 3" :class="active === 3 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Vay thành công thì bao lâu tiền đến tài khoản?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>Sau khi xét duyệt thông qua, chúng tôi sẽ giải ngân luôn và tiền giải ngân sẽ đến tài khoản của bạn ngay lập tức; Nếu vào các ngày nghỉ lễ thì tiền sẽ được giải ngân vào ngày làm việc sau đó.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 12 ? 0 : 12" :class="active === 12 ? 'active' : ''" id="#mobile">
                        <span class="_inline_block _wraper">
                            <img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%">
                            <img class="v_center" src="../../../static/img/support/right.png" width="60%">
                        </span> <span class="_333 v_center">Thao tác bước xác thực nhà mạng như thế nào?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>Bạn vui lòng xem ảnh hướng dẫn và thao tác theo các bước:</p>
                        <br/>
                        <img class="v_center" src="../../../static/img/support/help_phone_1.jpg" width="100%">
                        <img class="v_center" src="../../../static/img/support/help_phone_2.jpg" width="100%">
                        <img class="v_center" src="../../../static/img/support/help_phone_3.jpg" width="100%">
                        <img class="v_center" src="../../../static/img/support/help_phone_4.jpg" width="100%">
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 4 ? 0 : 4" :class="active === 4 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Có những phương thức thanh toán nào?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>Bạn có thể tra các phương thức thanh toán tại mục “Trang chủ - Thanh toán”. Bạn nên sử dụng thanh toán qua bên thứ 3 để được thanh toán nhanh chóng, tiện cho việc vay lại. Và bạn nên sử dụng những phương thức thanh toán hiển thị trong App để tránh bị lừa.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 5 ? 0 : 5" :class="active === 5 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Tại sao hạn mức vay tiền lại có sự điều chỉnh?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>Dữ liệu bạn gửi để đăng ký vay tạm thời không đáp ứng được tiêu chuẩn điểm đánh giá, hệ thống sẽ dựa theo điểm đánh giá của bạn để đưa ra sự điều chỉnh hợp lý, hi vọng bạn hiểu được, hạn mức thực tế bạn sẽ được hiển thị tại trang chủ.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 6 ? 0 : 6" :class="active === 6 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Làm thế nào để tăng hạn mức vay?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p> Bạn cần nộp dữ liệu chính xác và duy trì hạn mức tốt sẽ có lợi cho việc nâng cao hạn mức của bạn, hạn mức cao nhất lên đến 10.000.000.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 7 ? 0 : 7" :class="active === 7 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Tại sao đơn xin vay của tôi không được thông qua?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>  Bạn cần chắc chắn rằng thông tin bạn điền luôn chính xác, ảnh chụp CMT cần rõ và phù hợp với yêu cầu. Nếu như điểm tín dụng của bạn không đạt yêu cầu của hệ thống, điều này sẽ làm đăng ký của bạn không được thông qua.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 8 ? 0 : 8" :class="active === 8 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Quá hạn thanh toán sẽ bị ảnh hưởng gì?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>  Đến ngày thanh toán mà bạn chưa thanh toán hết số tiền cần trả thì sẽ bị cho là quá hạn. Khi quá hạn sẽ phát sinh thêm tiền phạt lãi suất, tiền nộp phạt, tiền quản lý sau vay, tiền quản lý danh bạ cũng như các khoản tiền phạt khác, đồng thời sẽ ảnh hưởng đến điểm tín dụng của bạn ở bên chúng tôi. Để duy trì tín dụng tốt, bạn cần thanh toán đúng thời hạn quy định.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 9 ? 0 : 9" :class="active === 9 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Vào ngày đến hạn, người vay có nhận được nhắc nhở thanh toán tiền vay không?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>Trước hạn thanh toán 01 ngày, App sẽ nhắc nhở người vay hạn thanh toán, nếu xuất hiện trường hợp đến hạn mà chưa thanh toán thì chúng tôi sẽ gọi điện nhắc nhở người vay thanh toán tiền vay. Nếu gặp trường hợp người vay không thanh toán tiền vay thì chúng tôi sẽ không bài trừ khả năng liên lạc với người thân của bạn để giục thanh toán, bởi vậy mong bạn duy trì lịch sử thanh toán tốt.</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 10 ? 0 : 10" :class="active === 10 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Làm thế nào để thay đổi số điện thoại?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>Tạm thời chúng tôi không hỗ trợ khách hàng tự thay đổi số điện thoại đăng ký, vui lòng liên hệ CSKH để thay đổi (Thời gian làm việc: 8:30 - 15:00).</p>
                    </div>
                    <h3 class="em_1 _cursor" @tap="active = active === 11 ? 0 : 11" :class="active === 11 ? 'active' : ''">
                        <span class="_inline_block _wraper"><img class="_hidden v_center" src="../../../static/img/support/top.png" width="100%"><img class="v_center" src="../../../static/img/support/right.png" width="60%"></span> <span class="_333 v_center">Làm thế nào để thay đổi thẻ ngân hàng đã liên kết?</span>
                    </h3>
                    <div class="_hidden padding info em__9">
                        <p>Bạn có thể thay đổi tại: Trang chủ-&gt; Trung tâm xác thực hoặc Tôi-&gt;Thẻ ngân hàng, liên kết lại.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import util from '@/util/util.js'

    export default {
        data() {
            return {
                active: 0
            }
        },
        methods: {
            onInit() {},
        },
        onLoad: function () {
            this.active = parseInt(util.getParam('item'));
        }
    }
</script>

<style lang="scss">
    .body {
        width: 100%;
        padding: 15px;
    }
    .row {
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -ms-flex-wrap: wrap;
        flex-wrap: wrap;
        margin-right: -15px;
        margin-left: -15px;
    }
    ._hidden {
        display: none;
    }
    .active {
        color: #222;
        img {display: none}
        ._hidden,
        + ._hidden{
            display: block;
        }
    }
    .col-6 {
        -ms-flex-preferred-size: 0;
        flex-basis: 0;
        -webkit-box-flex: 1;
        -ms-flex-positive: 1;
        flex-grow: 1;
        max-width: 100%;
        position: relative;
        width: 100%;
        min-height: 1px;
        padding-right: 15px;
        padding-left: 15px;
        padding-bottom: 15px;
        img {
            width: 40px;
            margin-right: 5px;
        }
        a {
            display: -webkit-box;
            display: -ms-flexbox;
            display: flex;
            align-items: center;
            text-decoration: none;
        }
    }
    h3 {
        border-bottom: 1px solid #ddd;
        display: flex;
        padding: 5px 0;
        align-items: center;
        color: #555;
        ._wraper {
            display: flex;
            min-width: 25px;
            height: 25px;
            align-items: center;
        }
        + div {
            border-bottom: 1px solid #ddd;
            padding: 12px;
            background-color: #fff;
            font-size: 13px;
            line-height: 1.5;
            color: #555;
        }
        img {
            width: 15px;
            height: auto;
            + img {
                height: 15px;
                width: auto;
            }
        }
    }
</style>

