<template><div><!-- ---
layout: Post
title: Bài 5. Mảng trong Java
subtitle: Lập trình Java căn bản
author: Theanishtar
date: 2023-06-06
useHeaderImage: false
headerImage: https://github.com/dangtranhuu/images/blob/main/angurvad/java-core/session5/banner.png?raw=true
headerMask: rgba(30, 69, 110, 0.61)
permalinkPattern: /ebook/java/java-core/:slug/
tags:
  - Java Core
---

Mảng là cấu trúc có các phần tử cùng kiểu và liền kề nhau trong bộ nhớ. Cùng mình tìm hiểu thông qua bài viết này nhé !!! -->
<!-- more -->
<h1 id="bai-5-mang" tabindex="-1"><a class="header-anchor" href="#bai-5-mang" aria-hidden="true">#</a> Bài 5. Mảng</h1>
<h2 id="_1-khai-niem" tabindex="-1"><a class="header-anchor" href="#_1-khai-niem" aria-hidden="true">#</a> 1. Khái niệm</h2>
<p>mảng dùng để lưu trữ nhiều giá trị trong một biến duy nhất, thay vì khai báo nhiều biến, khác với <a href="">danh sách liên kết</a> thì Mảng có các phần tử liền kề nhau trên thanh Ram vì vậy tiện lợi cho việc truy xuất dữ liệu !!!</p>
<h2 id="_2-khai-bao-mang" tabindex="-1"><a class="header-anchor" href="#_2-khai-bao-mang" aria-hidden="true">#</a> 2. Khai báo mảng</h2>
<p>Để khai báo một mảng, hãy xác định loại biến bằng dấu ngoặc vuông :</p>
<h3 id="khai-bao-khong-khoi-tao-phan-tu" tabindex="-1"><a class="header-anchor" href="#khai-bao-khong-khoi-tao-phan-tu" aria-hidden="true">#</a> Khai báo không khởi tạo phần tử</h3>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNums<span class="token punctuation">;</span> <span class="token comment">//mảng số nguyên </span>
<span class="token keyword">float</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myFloatNums<span class="token punctuation">;</span> <span class="token comment">//mảng số thực</span>
<span class="token class-name">String</span> myName<span class="token punctuation">;</span> <span class="token comment">//mảng chuỗi ký tự</span>
</code></pre></div><h3 id="khai-bao-co-khoi-tao-phan-tu" tabindex="-1"><a class="header-anchor" href="#khai-bao-co-khoi-tao-phan-tu" aria-hidden="true">#</a> Khai báo có khởi tạo phần tử</h3>
<p>khai báo các giá trị bằng dấu ngoặc nhọn:</p>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNums <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">//mảng số nguyên có 3 phần tử </span>
<span class="token keyword">float</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myFloatNums <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">3.45</span><span class="token punctuation">,</span> <span class="token number">1.23</span><span class="token punctuation">,</span> <span class="token number">6.74</span><span class="token punctuation">,</span> <span class="token number">8.4</span><span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">//mảng số thực có 4 phần tử</span>
<span class="token class-name">String</span> myName <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token string">"Đang"</span><span class="token punctuation">,</span><span class="token string">"Hữu"</span><span class="token punctuation">,</span><span class="token string">"Trần"</span><span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">//mảng chuỗi gồm 3 phần tử</span>
</code></pre></div><hr>
<h2 id="_3-cac-tinh-chat" tabindex="-1"><a class="header-anchor" href="#_3-cac-tinh-chat" aria-hidden="true">#</a> 3. Các tính chất</h2>
<details class="custom-container details"><summary>1. Vị trí bắt đầu là 0</summary>
<ul>
<li>Hình như có mỗi <a href="">Passcal</a>. là bắt đầu từ 1 đúng không ta 😆</li>
</ul>
</details>
<details class="custom-container details"><summary>2. Mảng không thể tự co dãn (có nghĩa là không thêm hay bớt phần tử được)</summary>
<ul>
<li>Các phần tử là cố định vì vậy bạn phải xác định đúng số lượng ngay từ khi khai báo mảng, để tránh việc dư thừa hay thiếu bộ nhớ nhé!!</li>
</ul>
</details>
<details class="custom-container details"><summary>3. Dữ liệu của mảng nằm liền kề nhau</summary>
<ul>
<li>Các địa chỉ phần tử nằm tuần tự thanh ghi và cách nhau <strong>4 byte</strong>, vì kích thước của <strong>int</strong> là <strong>4 byte</strong> (<RouterLink to="/post/2023/06/02/java-core-session2/"><em>xem thêm</em></RouterLink>)</li>
<li>Vì vậy bạn hoàn toàn có thể truy xuất tới phần tử bất kì trong mảng khi biết vị trí (index) của phần tử đó</li>
</ul>
</details>
<p>Chúng ta có thể thay đổi giá trị bằng cách truy xuất lại phần tử đó như sau :</p>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNums <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">5</span><span class="token punctuation">,</span><span class="token number">3</span><span class="token punctuation">,</span><span class="token number">7</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">9</span><span class="token punctuation">,</span><span class="token number">4</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
mmNums<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">2</span><span class="token punctuation">;</span>
<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">:</span> myNum<span class="token punctuation">)</span><span class="token punctuation">{</span>
   <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">print</span><span class="token punctuation">(</span>i <span class="token operator">+</span> <span class="token string">" "</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token comment">//output : 5 2 7 1 9 4</span>
</code></pre></div><hr>
<h2 id="_4-đo-dai-cua-mang" tabindex="-1"><a class="header-anchor" href="#_4-đo-dai-cua-mang" aria-hidden="true">#</a> 4. Độ dài của mảng</h2>
<details class="custom-container details"><summary>🤔 Như mình đã nói ở trên Mảng có chỉ số phần tử đầu tiên là 0. Vậy chỉ số cuối cùng là mấy ?</summary>
<ul>
<li>Java cung cấp cho ta một phương thức xác định vị trí cuối cùng của Mảng đó là <strong>length</strong></li>
</ul>
</details>
<p>Sử dụng <em>phương thức</em> <strong>length</strong> để kiểm tra độ dài của mảng như sau :</p>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNums <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">9</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">println</span><span class="token punctuation">(</span><span class="token string">"Mảng có "</span> <span class="token operator">+</span> myNums<span class="token punctuation">.</span>length <span class="token operator">+</span> <span class="token string">" phần tử"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token comment">// output : Mảng có 6 phần tử</span>
</code></pre></div><blockquote>
<p>Ở <strong>String</strong> là <em>length()</em> còn <strong>Arrays</strong> là <em>length</em></p>
</blockquote>
<hr>
<h2 id="_5-duyet-mang" tabindex="-1"><a class="header-anchor" href="#_5-duyet-mang" aria-hidden="true">#</a> 5. Duyệt mảng</h2>
<p>Mảng là <a href="">cấu trúc dữ liệu</a> có thể xác định được giá trị đầu (<em>0</em>) và giá trị cuối (<em>length</em>) vì vậy sẽ thuận tiện hơn nếu bạn dùng vòng lặp <strong>for</strong> hoặc <strong>forEach</strong> để duyệt mảng</p>
<h3 id="vong-lap-for" tabindex="-1"><a class="header-anchor" href="#vong-lap-for" aria-hidden="true">#</a> Vòng lặp for</h3>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNums <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">9</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">0</span> <span class="token punctuation">;</span> i <span class="token operator">&lt;</span> myNums<span class="token punctuation">.</span><span class="token function">length</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
   <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">print</span><span class="token punctuation">(</span>i <span class="token operator">+</span> <span class="token string">" "</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token comment">//output : 5 3 7 1 9 4</span>
</code></pre></div><h3 id="vong-lap-foreach" tabindex="-1"><a class="header-anchor" href="#vong-lap-foreach" aria-hidden="true">#</a> Vòng lặp forEach</h3>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNums <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">9</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">:</span> myNums<span class="token punctuation">)</span><span class="token punctuation">{</span>
   <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">print</span><span class="token punctuation">(</span>i <span class="token operator">+</span> <span class="token string">" "</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token comment">//output : 5 3 7 1 9 4</span>
</code></pre></div><blockquote>
<p>💡 Cả 2 đều có thể sử dụn nhưng tôi khuyên bạn nên xài *<strong>for..Each</strong> trong trường hợp dễ.</p>
</blockquote>
<hr>
<h2 id="_6-mang-đa-chieu" tabindex="-1"><a class="header-anchor" href="#_6-mang-đa-chieu" aria-hidden="true">#</a> 6. Mảng đa chiều</h2>
<p>Có nghĩa là 1 mảng, mỗi phần tử trong mảng đó đều chứa thêm 1 mảng.</p>
<blockquote>
<p>💡 Nói đơn giản <strong>Ma trận</strong> là mảng 2 chiều, và chúng ta chỉ học tới mảng 2 chiều thôi</p>
</blockquote>
<h3 id="vi-du-mang-2-chieu" tabindex="-1"><a class="header-anchor" href="#vi-du-mang-2-chieu" aria-hidden="true">#</a> Ví dụ mảng 2 chiều</h3>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNumbers <span class="token operator">=</span> <span class="token punctuation">{</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">6</span><span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">}</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre></div><p>💡 Muốn truy xuất trong mảng 2 chiều ta vẫn dùng như trên, ví dụ lấy số 3 ⇨ <strong>myNumbers = [0][2]</strong></p>
<p>💡 Nếu bạn muốn duyệt qua mảng 2 chiều phải dòng 2 vòng lặp lồng nhau như sau có 2 cách như sau :</p>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNumbers <span class="token operator">=</span> <span class="token punctuation">{</span> <span class="token punctuation">{</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span> <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">6</span><span class="token punctuation">,</span> <span class="token number">7</span> <span class="token punctuation">}</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> myNumbers<span class="token punctuation">.</span>length<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
   <span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> j <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> j <span class="token operator">&lt;</span> myNumbers<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">.</span>length<span class="token punctuation">;</span> j<span class="token operator">++</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
   	<span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">print</span><span class="token punctuation">(</span>myNumbers<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">[</span>j<span class="token punctuation">]</span> <span class="token operator">+</span> <span class="token string">" "</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
   <span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token comment">// output : 1 2 3 4 5 6 7</span>
</code></pre></div><div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNumbers <span class="token operator">=</span> <span class="token punctuation">{</span> <span class="token punctuation">{</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span> <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">6</span><span class="token punctuation">,</span> <span class="token number">7</span> <span class="token punctuation">}</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> subArray <span class="token operator">:</span> myNumbers<span class="token punctuation">)</span> <span class="token punctuation">{</span>
   <span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">:</span> subArray<span class="token punctuation">)</span> <span class="token punctuation">{</span>
      <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">print</span><span class="token punctuation">(</span>i <span class="token operator">+</span> <span class="token string">" "</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
   <span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token comment">// output : 1 2 3 4 5 6 7</span>
</code></pre></div><h3 id="vi-du-mang-3-chieu" tabindex="-1"><a class="header-anchor" href="#vi-du-mang-3-chieu" aria-hidden="true">#</a> Ví dụ mảng 3 chiều</h3>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token punctuation">]</span> myNumbers <span class="token operator">=</span> <span class="token punctuation">{</span> <span class="token punctuation">{</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">2</span><span class="token punctuation">,</span><span class="token number">3</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">2</span><span class="token punctuation">,</span><span class="token number">3</span><span class="token punctuation">}</span> <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span> <span class="token punctuation">{</span><span class="token number">2</span><span class="token punctuation">,</span><span class="token number">4</span><span class="token punctuation">,</span><span class="token number">6</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">6</span><span class="token punctuation">,</span><span class="token number">8</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">5</span><span class="token punctuation">,</span><span class="token number">7</span><span class="token punctuation">}</span> <span class="token punctuation">}</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre></div><blockquote>
<p>🚀 Mảng 3 chiều biết cho có thôi nhé, Mảng 2 chiều đã đủ rồi</p>
</blockquote>
<h2 id="_7-bai-tap" tabindex="-1"><a class="header-anchor" href="#_7-bai-tap" aria-hidden="true">#</a> 7. Bài tập</h2>
<h3 id="_7-1-dung-vong-lap-for-đe-tinh-tong-cac-so-trong-mang" tabindex="-1"><a class="header-anchor" href="#_7-1-dung-vong-lap-for-đe-tinh-tong-cac-so-trong-mang" aria-hidden="true">#</a> 7.1 Dùng vòng lặp For để tính tổng các số trong mảng</h3>
<p>Đơn giản nhất các bạn chỉ cần dùng dòng lặp For hoặc ForEach để duyệt qua mảng, và dùng một biến tổng để cộng dồn các giá trị sau mỗi lần duyệt là xong</p>
<details class="custom-container details"><summary>Bài giải 7.1</summary>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">class</span> <span class="token class-name">TinhTongTrongMang</span><span class="token punctuation">{</span>
    <span class="token keyword">public</span> <span class="token keyword">static</span> <span class="token keyword">void</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token class-name">String</span> args<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
        <span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> array <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">10</span><span class="token punctuation">,</span> <span class="token number">20</span><span class="token punctuation">,</span> <span class="token number">30</span><span class="token punctuation">,</span> <span class="token number">40</span><span class="token punctuation">,</span> <span class="token number">50</span><span class="token punctuation">,</span> <span class="token number">10</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
        <span class="token keyword">int</span> sum <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
        <span class="token comment">//Advanced for loop</span>
        <span class="token keyword">for</span><span class="token punctuation">(</span> <span class="token keyword">int</span> num <span class="token operator">:</span> array<span class="token punctuation">)</span> <span class="token punctuation">{</span>
            sum <span class="token operator">=</span> sum<span class="token operator">+</span>num<span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
        <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">println</span><span class="token punctuation">(</span><span class="token string">"Kết quả là:"</span><span class="token operator">+</span>sum<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span>

<span class="token comment">// Ouput: Tổng là 160</span>
</code></pre></div></details>
<h3 id="_7-2-đao-nguoc-cac-phan-tu-trong-mang" tabindex="-1"><a class="header-anchor" href="#_7-2-đao-nguoc-cac-phan-tu-trong-mang" aria-hidden="true">#</a> 7.2 Đảo ngược các phần tử trong mảng.</h3>
<p>Trong bài tập này chúng ta sẽ thực hiện chương trình đảo ngược các phần tử trong mảng Java. Với bài tập này giúp các bạn hiểu rõ hơn về mảng để có thể làm các bài tập phức tạp hơn.</p>
<p>Cụ thể trong chương trình này chúng ta sẽ thực hiện một chương trình đảo ngược các phần tử, ví dụ người dùng nhập vào các số 1,2,3,4,5 thì chương trình sẽ đảo ngược thành 5,4,3,2,1. Để hiểu được chương trình này các bạn phải biết về mảng, vòng lặp For và While.</p>
<p>Ở ví dụ này chúng ta sẽ sử dụng vòng lặp For để yêu cầu người dùng nhập vào giá trị cho các phần tử, sau đó dùng vòng lặp While để đảo ngược các vị trí của các phần tử trong mảng.</p>
<details class="custom-container details"><summary>Bài giải 7.2</summary>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">public</span> <span class="token keyword">class</span> <span class="token class-name">DaoNguocTrongMang</span><span class="token punctuation">{</span>
    <span class="token keyword">public</span> <span class="token keyword">static</span> <span class="token keyword">void</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token class-name">String</span> args<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
        <span class="token keyword">int</span> counter<span class="token punctuation">,</span> i<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">,</span> j<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">,</span> temp<span class="token punctuation">;</span>
        <span class="token keyword">int</span> number<span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">10</span><span class="token punctuation">,</span> <span class="token number">20</span><span class="token punctuation">,</span> <span class="token number">30</span><span class="token punctuation">,</span> <span class="token number">40</span><span class="token punctuation">,</span> <span class="token number">50</span><span class="token punctuation">,</span> <span class="token number">10</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
        counter <span class="token operator">=</span> scanner<span class="token punctuation">.</span><span class="token function">nextInt</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        j <span class="token operator">=</span> i <span class="token operator">-</span> <span class="token number">1</span><span class="token punctuation">;</span>
        i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
        <span class="token keyword">while</span><span class="token punctuation">(</span>i<span class="token operator">&lt;</span>j<span class="token punctuation">)</span><span class="token punctuation">{</span>
            temp <span class="token operator">=</span> number<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
            number<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> number<span class="token punctuation">[</span>j<span class="token punctuation">]</span><span class="token punctuation">;</span>
            number<span class="token punctuation">[</span>j<span class="token punctuation">]</span> <span class="token operator">=</span> temp<span class="token punctuation">;</span>
            i<span class="token operator">++</span><span class="token punctuation">;</span>
            j<span class="token operator">--</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
        <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">print</span><span class="token punctuation">(</span><span class="token string">"Mảng sau khi đảo ngược: "</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token keyword">for</span><span class="token punctuation">(</span>i<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">;</span> i<span class="token operator">&lt;</span>counter<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
            <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">print</span><span class="token punctuation">(</span>number<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token operator">+</span> <span class="token string">"  "</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token comment">// Output: Mảng sau khi đảo ngược: 10 50 40 30 20 10</span>
</code></pre></div></details>
<h3 id="_7-3-in-cac-phan-tu-trung-nhau-trong-mang" tabindex="-1"><a class="header-anchor" href="#_7-3-in-cac-phan-tu-trung-nhau-trong-mang" aria-hidden="true">#</a> 7.3 In các phần tử trùng nhau trong mảng</h3>
<p>Để in ra các phần tử trùng nhau thì chúng ta thực hiện trong 4 bước:</p>
<ul>
<li>Bước 1: Khởi tạo mảng arr[] = {1, 2, 3, 4, 2, 7, 8, 8, 3}.</li>
<li>Bước 2: Triển khai vòng for i tăng dần, duyệt từ đầu đến cuối mảng arr[].</li>
<li>Bước 3: Triển khai vòng for j(ở trong vòng for i) bắt đầu tăng dần từ i đến hết.</li>
<li>Bước 4: Duyệt 2 vòng for, nếu arr[i] == arr[j] thì in arr[j]</li>
<li>Trên đây là 4 bước cơ bản của thuật toán xử lí bài toán: In các phần tử trùng lặp trong Java.</li>
</ul>
<p>Tiếp theo chúng ta triển khai code theo thuật toán vừa nêu.</p>
<details class="custom-container details"><summary>Bài giải 7.3</summary>
<div class="language-java ext-java"><pre v-pre class="language-java"><code><span class="token keyword">public</span> <span class="token keyword">class</span> <span class="token class-name">DuplicateElement</span> <span class="token punctuation">{</span>   
<span class="token keyword">public</span> <span class="token keyword">static</span> <span class="token keyword">void</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token class-name">String</span><span class="token punctuation">[</span><span class="token punctuation">]</span> args<span class="token punctuation">)</span> <span class="token punctuation">{</span>    
        <span class="token comment">//Khởi tạo mảng  </span>
        <span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> arr <span class="token operator">=</span>  <span class="token keyword">new</span> <span class="token keyword">int</span><span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token punctuation">{</span> <span class="token number">1</span> <span class="token punctuation">,</span>  <span class="token number">2</span> <span class="token punctuation">,</span>  <span class="token number">3</span> <span class="token punctuation">,</span>  <span class="token number">4</span> <span class="token punctuation">,</span>  <span class="token number">2</span> <span class="token punctuation">,</span>  <span class="token number">7</span> <span class="token punctuation">,</span>  <span class="token number">8</span> <span class="token punctuation">,</span>  <span class="token number">8</span> <span class="token punctuation">,</span>  <span class="token number">3</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>   
        <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">println</span><span class="token punctuation">(</span> <span class="token string">"Các phần tử trùng nhau trong mảng đã cho: "</span> <span class="token punctuation">)</span><span class="token punctuation">;</span>  
        <span class="token comment">//Tìm kiếm phần tử trùng lặp  </span>
        <span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> arr<span class="token punctuation">.</span>length<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>  
            <span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> j <span class="token operator">=</span> i <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">;</span> j <span class="token operator">&lt;</span> arr<span class="token punctuation">.</span>length<span class="token punctuation">;</span> j<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>  
                <span class="token keyword">if</span><span class="token punctuation">(</span>arr<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">==</span> arr<span class="token punctuation">[</span>j<span class="token punctuation">]</span><span class="token punctuation">)</span>  
                    <span class="token class-name">System</span><span class="token punctuation">.</span>out<span class="token punctuation">.</span><span class="token function">print</span><span class="token punctuation">(</span>arr<span class="token punctuation">[</span>j<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>  
            <span class="token punctuation">}</span>  
        <span class="token punctuation">}</span>  
    <span class="token punctuation">}</span>  
<span class="token punctuation">}</span>

<span class="token comment">// Output: Các phần tử trùng nhau trong mảng đã cho: 2 3 8</span>
</code></pre></div></details>
</div></template>
