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
                    <h3 @tap="active = active === 99 ? 0 : 99" :class="active === 99 ? 'active' : ''">
                        <span>
                            <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                            <img src="../../../static/img/support/right.png" width="60%">
                        </span>
                        <span>Vấn đề vay tiền</span>
                    </h3>
                    <div class="_hidden">
                        <h3 @tap="active1 = active1 === 1 ? 0 : 1" :class="active1 === 1 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>1. Cần cung cấp thông tin gì khi vay?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Tất cả quy trình vay được thực hiện trên điện thoại của bạn, bạn chỉ cần chuẩn bị chứng minh thư và thao tác theo hướng dẫn trên điện thoại là được.
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 2 ? 0 : 2" :class="active1 === 2 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>2. Phải làm sao khi việc kiểm tra CMT không thành công?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Vui lòng kiểm tra quyền truy cập camera trên điện thoại của bạn và xóa bộ nhớ dữ liệu cake rồi thử lại. Đồng thời thao tác nơi có ánh sáng tốt, ánh sáng yếu có thể ảnh hưởng đến chất lượng ảnh. Nếu vẫn không thành công thì bạn vui lòng liên hệ lại bên CSKH của App để được hỗ trợ.
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 3 ? 0 : 3" :class="active1 === 3 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>3. Làm sao để kiểm tra mật khẩu nhà mạng?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Có 2 cách để kiểm tra mật khẩu nhà mạng:<br>
                                1) Bạn có thể gọi điện cho CSKH của nhà mạng điện thoại, kiểm tra lại mật khẩu nhà mạng của bạn<br>
                                Viettel: <a href="tel:18008098"> 18008098</a><br>
                                Vinaphone: <a href="tel:18001091"> 18001091</a><br>
                                Mobiphone: <a href="tel:9090"> 9090</a>
                            </p>
                            <p>
                                2) Bạn có thể đăng nhập trên trang web trực tuyến nhà mạng và lấy mật khẩu truy vấn (mật khẩu đăng nhập) cho số điện thoại di động của bạn.
                            </p>
                            <p>
                                3）Vui lòng đảm bảo rằng mật khẩu đăng nhập trên trang web chính thức của nhà mạng và trên APP giống nhau.
                            </p>
                            <p>
                                4）<a @tap="goto">Xem hướng dẫn</a>
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 4 ? 0 : 4" :class="active1 === 4 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>4. Không thông qua xác thực nhà mạng?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Vui lòng kiểm tra xem SDT bạn sử dụng trong bước này phải là SDT đăng ký ứng dụng không. Chúng tôi chỉ cho phép sử dụng SDT đã đăng ký để thực hiện bước này.
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 5 ? 0 : 5" :class="active1 === 5 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>5. Liên kết thẻ ngân hàng thất bại?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Nếu SDT dùng đăng ký cho thẻ ngân hàng không giống với SDT bạn đã đăng ký trên ứng dụng thì sẽ dẫn đến liên kết thẻ ngân hàng không thành công. Hệ thống ngân hàng xảy ra lỗi vv cũng có thể dẫn đến sự thất bại của bước này, bạn nên đổi thẻ ngân hàng khác để thực hiện. Bạn có thể liên hệ lại với bên ngân hàng để đổi SDT đăng ký hoặc xin đổi thẻ khác.
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 6 ? 0 : 6" :class="active1 === 6 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>6. Thông tin vay điền sai có thể sửa lại được không?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Không thể sửa lại.
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 7 ? 0 : 7" :class="active1 === 7 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>7. Có thể hủy đơn vay sau khi đã gửi không?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Đơn xin vay thường không thể hủy sau khi nộp.<br>
                                Nếu trạng thái đơn xin vay tiền của bạn là "đang xét duyệt", khi nhân viên xét duyệt liên lạc bạn có thể yêu cầu hủy.<br>
                                Nếu trạng thái đơn xin vay tiền của bạn là "xét duyệt thông qua", "đang giải ngân" hoặc "giải ngân thành công"thì khoản vay đã được giải ngân đi thành công và không thể hủy bỏ.
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 8 ? 0 : 8" :class="active1 === 8 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>8. Tôi có thể đăng ký nhiều tài khoản để vay tiền không?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Không, một người chỉ có thể sử dụng một tài khoản. Nếu bạn sử dụng nhiều tài khoản để vay tiền, chúng tôi sẽ từ chối đơn xin vay tiền của bạn.
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 9 ? 0 : 9" :class="active1 === 9 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>9. Điền sai số CMT phải làm sao?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Bạn có thể liên hệ với chăm sóc khách hàng của chúng tôi:<br>
                                Gửi thông tin liên quan qua email và chúng tôi sẽ xác minh và thay đổi thông tin cho bạn<br>
                                Email xác minh dữ liệu: <a href="mailto:khovay2018@gmail.com">khovay2018@gmail.com</a>
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 10 ? 0 : 10" :class="active1 === 10 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>10. Làm cách nào để thay đổi thẻ ngân hàng?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Trên cơ sở là không có khoản vay hoặc khoản vay được giải quyết, bạn có thể liên hệ với chăm sóc khách hàng của chúng tôi:
                            </p>
                        </div>

                        <h3 @tap="active1 = active1 === 11 ? 0 : 11" :class="active1 === 11 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>11. Làm cách nào để cập nhật thông tin liên hệ của tôi?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Bạn có thể liên hệ với chăm sóc khách hàng của chúng tôi.
                            </p>
                        </div>
                    </div>

                    <h3 @tap="active = active === 2 ? 0 : 2" :class="active === 2 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                        <span>Vấn đề xét duyệt</span>
                    </h3>
                    <div class="_hidden">
                        <h3 @tap="active2 = active2 === 1 ? 0 : 1" :class="active2 === 1 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>1. Thời gian xét duyệt</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Vui lòng điền thông tin cẩn thận. Sau khi bạn gửi đơn xin vay tiền:<br>
                                1) Nếu thông tin của bạn là đúng và đầy đủ, hệ thống sẽ tự động xét duyệt (trong vòng 5 phút)<br>
                                2) Nếu thông tin của bạn không đầy đủ hoặc vì lý do khác (thường trong vòng 24 giờ)<br>

                            </p>
                        </div>

                        <h3 @tap="active2 = active2 === 2 ? 0 : 2" :class="active2 === 2 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>2. Bao lâu thì nhận được kết quả xét duyệt</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Kết quả xét duyệt sẽ có trong vòng 24 giờ sau khi nộp đơn. Vui lòng chú ý trạng thái trên APP , nếu vào cuối tuần hoặc ngày lễ có thể sẽ lâu hơn. Việc không kịp thời trả lời cuộc gọi từ người xét duyệt cũng sẽ ảnh hưởng đến tiến độ xét duyệt. Vui lòng chú ý đến cuộc gọi và kiên nhẫn chờ đợi kết quả đánh giá.
                            </p>
                        </div>

                        <h3 @tap="active2 = active2 === 3 ? 0 : 3" :class="active2 === 3 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>3. Tại sao tôi đã nộp đơn trong nhiều ngày và chưa nhận được kết quả đánh giá?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Thời gian bình thường để xét duyệt là 24 giờ ,Trong trường hợp ngày lễ hoặc sự kiện, quá trình xét duyệt có thể bị trì hoãn. Vui lòng thông cảm và kiên nhẫn chờ đợi.
                            </p>
                        </div>

                        <h3 @tap="active2 = active2 === 4 ? 0 : 4" :class="active2 === 4 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>4. Điều gì xảy ra nếu trả lời sai / bỏ lỡ người xét duyệt gọi điện xác thực?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Người phê duyệt sẽ dựa trên tình hình chung để đánh giá xem có cần liên hệ lại hay không Vui lòng chú ý đến điện thoại hoặc kiểm tra kết quả xét duyệt sau đó. Bạn cũng có thể để lại lý do cho chúng tôi qua mục tin nhắn
                            </p>
                        </div>
                    </div>

                    <h3 @tap="active = active === 3 ? 0 : 3" :class="active === 3 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                        <span>Giải ngân, thanh toán</span>
                    </h3>
                    <div class="_hidden">
                        <h3 @tap="active3 = active3 === 1 ? 0 : 1" :class="active3 === 1 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>1. Giải ngân qua thẻ ngân hàng nào?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Chỉ giải ngân qua thẻ ngân hàng đăng ký trên App
                            </p>
                        </div>

                        <h3 @tap="active3 = active3 === 2 ? 0 : 2" :class="active3 === 2 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>2. Giải ngân bao lâu thì nhận được tiền?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Về nguyên tắc, hệ thống tự động giải ngân và nhận tiền ngay sau đó. Tuy nhiên, không loại trừ một số trường hợp đặc biệt , tùy thuộc vào tốc độ xử lý thanh toán ngân hàng của thẻ ngân hàng của bạn
                            </p>
                        </div>

                        <h3 @tap="active3 = active3 === 3 ? 0 : 3" :class="active3 === 3 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>3. Ngày nghỉ, ngày lễ có giải ngân không?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Với những người mới đăng ký cuối tuần và ngày lễ thường bị trì hoãn , khách vay cũ sẽ giải ngân bình thường.
                            </p>
                        </div>

                        <h3 @tap="active3 = active3 === 4 ? 0 : 4" :class="active3 === 4 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>4. Tiền lãi sẽ bắt đầu tính từ ngày nào?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Sau khi khoản vay của bạn được thông qua và ấn vào nút "xin vay", tiền lãi sẽ được tính từ ngày khoản vay được giải ngân vào số dư tài khoản của bạn.
                            </p>
                        </div>

                        <h3 @tap="active3 = active3 === 5 ? 0 : 5" :class="active3 === 5 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>5. Có những hình thức thanh toán nào?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Bạn có thể thanh toán thông qua các phương thức được hiện trên App<br>
                                Lựa chọn phương thức thanh toán:<br>
                                1) Thanh toán qua bên thứ 3<br>
                                2) Trả nợ bằng cách chuyển tiền vào tài khoản ngân hàng:<br>
                                Chuyển số tiền trả nợ vào tài khoản và lưu ý tên APP + số điện thoại di động đã đăng ký.<br>
                                Lưu ý:<br>
                                1) Bằng cách thanh toán qua bên thứ 3 có thể được xác nhận ngay lập tức và có thể tiếp tục vay lại<br>
                                2) Việc hoàn trả bằng cách chuyển tiền vào tài khoản ngân hàng không được xác nhận theo thời gian thực. Thời gian thực tế của khoản thanh toán được dựa trên thời gian thực tế chuyển khoản của ngân hàng (1 đến 2 ngày làm việc). Người dùng cần vay lại luôn nên chọn cách thanh toán qua bên thứ 3 để không ảnh hưởng đến nhu cầu sử dụng của bạn.<br>
                                Nếu bạn có bất kỳ câu hỏi trong quá trìnht hực hiện xin vui lòng liên hệ với dịch vụ khách hàng.<br>
                            </p>
                        </div>

                        <h3 @tap="active3 = active3 === 6 ? 0 : 6" :class="active3 === 6 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>6. Cảnh giác khi thanh toán?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Việc thanh toán chỉ được thực hiện thông qua phương thức liệt kê trong APP. Bất kỳ phương thức thanh toán hoặc tài khoản nào khác ngoài APP không phải của chúng tôi. Cảnh giác với việc bị lừa và không nên tin vào tài khoản thông báo thanh toán gửi về SDT của bạn (vui lòng kiểm tra cẩn thận).
                            </p>
                        </div>

                        <h3 @tap="active3 = active3 === 7 ? 0 : 7" :class="active3 === 7 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>7. Tôi có thể thanh toán đầy đủ trước không? Có mất phí không?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Bạn có thể đăng nhập vào APP để xem kế hoạch thanh toán. Trả nợ trước, tất cả các khoản phí được hiển thị trong kế hoạch thanh toán.
                            </p>
                        </div>

                        <h3 @tap="active3 = active3 === 8 ? 0 : 8" :class="active3 === 8 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>8. Nếu quá hạn thì làm thế nào?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Người vay thực hiện nghiêm túc nghĩa vụ trả nợ. Người vay không thanh toán đầy đủ vào ngày được quy định trong hợp đồng cho vay, dẫn đến quá hạn và người vay phải trả lãi quá hạn. Trong trường hợp quá hạn, vui lòng thực hiện thanh toán thủ công bằng APP hoặc tham khảo dịch vụ khách hàng để hỗ trợ thanh toán
                            </p>
                        </div>
                    </div>

                    <h3 @tap="active = active === 4 ? 0 : 4" :class="active === 4 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                        <span>Vấn đề khác</span>
                    </h3>
                    <div class="_hidden">
                        <h3 @tap="active4 = active4 === 1 ? 0 : 1" :class="active4 === 1 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>1. Hạn mức vay</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Chúng tôi giới hạn hạn mức với người vay lần đầu. Khi bạn thanh toán đúng hạn, chúng tôi sẽ tự động tăng hạn mức của bạn. Tất nhiên, nếu bạn không thanh toán đúng hạn, hệ thống sẽ tự động giảm hạn mức của bạn.
                            </p>
                        </div>

                        <h3 @tap="active4 = active4 === 2 ? 0 : 2" :class="active4 === 2 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>2. Vay có an toàn không?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                APP ký thỏa thuận điện tử với bạn, dựa vào các thuật toán dữ liệu hàng đầu trong ngành để mã hóa tất cả dữ liệu của bạn để đảm bảo an toàn cho quá trình trao đổi và lưu trữ thông tin và các quyền hợp pháp của bạn đảm bảo được bảo vệ hoàn toàn.
                            </p>
                        </div>

                        <h3 @tap="active4 = active4 === 3 ? 0 : 3" :class="active4 === 3 ? 'active' : ''">
                            <span>
                                <img class="_hidden" src="../../../static/img/support/top.png" width="100%">
                                <img src="../../../static/img/support/right.png" width="60%">
                            </span>
                            <span>3. Hiện tại App đang hỗ trợ cho những thành phố nào?</span>
                        </h3>
                        <div class="_hidden">
                            <p>
                                Hiện tại hỗ trợ cho toàn bộ các tỉnh thành tại Việt Nam
                            </p>
                        </div>
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
                active: 0,
                active1: 0,
                active2: 0,
                active3: 0,
                active4: 0,
                active5: 0,
                active6: 0,
            }
        },
        methods: {
            onInit() {},
            goto() {
                uni.navigateTo({
                    url: 'phone'
                });
            }
        },
        onLoad: function () {
            this.active = parseInt(util.getParam('item'));
        }
    }
</script>

<style lang="scss">
    * {
        font-family: "Times New Roman";
    }
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
    #question_wraper >div >h3 {
        text-transform: uppercase;
    }
    #question_wraper > div {
        border-bottom: 1px solid #ddd;
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
        * {
            font-size: 11px;
        }
    }
    h3 {
        border-top: 1px solid #ddd;
        display: flex;
        padding: 8px 0;
        align-items: center;
        color: #111;
        >span {
            display: flex;
            min-width: 25px;
            height: 25px;
            align-items: center;
            justify-content: center;
        }
        + div {
            border-top: 1px solid #ddd;
            padding: 0;
            background-color: #fff;
            font-size: 13px;
            line-height: 1.5;
            color: #333;
            h3 {
                color: #333;
                background-color: #f8f8f8;
                padding-left: 6px;
                >span {
                    min-width: 20px;
                    height: 20px;
                }
                img {
                    width: 12px;
                    height: auto;
                    + img {
                        height: 12px;
                        width: auto;
                    }
                }
            }
            h3:first-child {
                border-top: 0;
            }
            h3 + div {
                padding: 6px 12px 10px 18px;
            }
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
    a {
        color: #1aad19;
        text-decoration: none;
    }
</style>

