# 关于二次探测如何保证探测到表所有项的证明
> 共有两种形式的二次探测，分别为<br>
> ![image](https://user-images.githubusercontent.com/23076538/145684221-20ae5c73-2bd9-4fab-95b5-0e0bdadd1870.png)<br>
> ![image](https://user-images.githubusercontent.com/23076538/146514368-863873da-8411-4fbb-b179-861a2f71649e.png)&emsp;*(此证明仅讨论此形式)*

## 一、预备知识
### 二次剩余
当存在某个&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684283-b04b75c1-6dff-424d-9abc-5dac2b6c5818.png)&nbsp;，
令式子&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684330-4f7ae193-20ef-4695-ac0a-b76092423e80.png)&nbsp;的
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684283-b04b75c1-6dff-424d-9abc-5dac2b6c5818.png)&nbsp;有解时，称
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684404-e930ea7c-0492-4f83-924b-e7da271a790e.png)&nbsp;是模
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的二次剩余；当
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684283-b04b75c1-6dff-424d-9abc-5dac2b6c5818.png)&nbsp;无解时，称
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684404-e930ea7c-0492-4f83-924b-e7da271a790e.png)&nbsp;是模
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的二次非剩余。<br><br>
列出一张&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685570-efe9e14f-d0fd-45e0-82d7-48a3dc4dbf57.png)&nbsp;的二次剩余列表如下：<br>
| d       | 1   |  2  |  3 |  4  |  5  |  6  |  7  |  8 |  9  |  10  |  11  |  12  |  13  |  14  |
| :----:   | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  | :----:  |
| d^2 | 1 | 4| 9 | 16|25|36|49|64|81|100|121|144|169|196|
| mod 2 | 1 | 0| 1 | 0|1|0|1|0|1|0|1|0|1|0|
| mod 3 | 1 | 1| 0 | 1|1|0|1|1|0|1|1|0|1|1|
| mod 4 | 1 | 0| 1 | 0|1|0|1|0|1|0|1|0|1|0|
| mod 5 | 1 | 4| 4 | 1|0| 1 | 4| 4 | 1|0| 1 | 4| 4 | 1|
| mod 6 | 1 | 4| 3 | 4|1| 0 | 1 | 4| 3 | 4|1| 0 | 1 | 4|
| mod 7 | 1 | 4| 2| 2|4| 1 | 0 | 1 | 4| 2| 2|4| 1 | 0 |
| mod 8 | 1 | 4| 1| 0| 1 | 4| 1| 0| 1 | 4| 1| 0| 1 | 4|
| mod 9 | 1 | 4| 0| 7| 7 | 0| 4| 1| 0 | 1 | 4| 0| 7| 7|
| mod 10| 1 | 4| 9| 6|5| 6| 9|4|1|0| 1| 4| 9| 6|
| mod 11| 1 | 4| 9 | 5|3| 3 | 5| 9 | 4|1| 0 | 1| 4 | 9|

从表中我们可以看出一些规律。首先，剩余数以&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;
的长度为一个段一个段地轮回，这很好理解，因为取模为&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;时，
其值必然小于等于&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;；其次，在这一段的剩余数中，
左右两边是对称的，如mod 7时的1、4、2与2、4、1是对称的，也就是说，mod 7时的二次剩余只有3个。<br>

### 费马小定律
设&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;为素数，
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;是任意整数，且不为
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的倍数，则有
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685944-01d26dc4-6488-4e16-99c5-bbfd6df09f99.png)&nbsp;。<br>

先证明一个引理：设&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;为素数，
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;是任意整数，且不为
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的倍数，则有序列
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686199-7950d3f2-78bc-4961-88c7-2b645ffcac50.png)&nbsp;与序列
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686225-94371e52-f252-4c50-8689-d8efada2eb9b.png)&nbsp;不考虑顺序时等价。<br>

假如序列
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686327-b8a7e79e-38aa-45f0-9344-a7d638eacc54.png)&nbsp;存在
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686410-cdf3b1dd-4cb7-4619-ac49-ea6e907a5eb4.png)&nbsp;重复，也即
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686485-a530c324-920a-4f17-b9b9-1208ce2f703c.png)&nbsp;，由于
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;不能被
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;整除，即只能是
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686551-6d2e78db-1de4-4787-b643-be0ddde158e9.png)&nbsp;被
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;整除，又因为
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686602-6522b38d-c377-49cc-9c1e-379a18e6d2e7.png)&nbsp;，所以
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686652-762c445c-0762-4319-884d-e00ab67e943d.png)&nbsp;，能被
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;整除的情况只能是
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686671-8445072e-16d9-4937-b4fb-b81b2f16e187.png)&nbsp;，也就是说存在重复只能是两个值就是同一个的情况，
即序列&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686327-b8a7e79e-38aa-45f0-9344-a7d638eacc54.png)&nbsp;元素均在
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686761-3a674a6d-88be-4874-be90-df075e242475.png)&nbsp;以内，且不重复，即与序列
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686775-0fd86ceb-d312-4d2d-9419-13019502fa1f.png)&nbsp;不考虑顺序时等价。<br>

根据引理，将序列
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686327-b8a7e79e-38aa-45f0-9344-a7d638eacc54.png)&nbsp;与序列
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686775-0fd86ceb-d312-4d2d-9419-13019502fa1f.png)&nbsp;元素分别累乘取模
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;，两边应该是相等的，也即
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686956-02443756-ae1d-4be6-88d3-f3e4b90fd37d.png)&nbsp;

### 欧拉判别法则
若&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;是模
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的二次剩余，则有
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145687102-05c2b191-8369-4622-a79f-4edc414abc0e.png)&nbsp;；若
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;是模
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的二次非剩余，则有
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145687125-56a02ae5-6134-486b-a99d-c73ac3069003.png)&nbsp;。<br>

因为&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;是模
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的二次剩余，有
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145687344-4fbbce76-490d-4ed9-ab10-3de93e422fc5.png)&nbsp;，
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;不为0，则
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145687399-aa1c2f12-fb66-483a-baf8-c751d833c5e6.png)&nbsp;不能被
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;整除，则
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684283-b04b75c1-6dff-424d-9abc-5dac2b6c5818.png)&nbsp;不能被
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;整除。<br>

根据费马小定律，有&nbsp;![image](https://user-images.githubusercontent.com/23076538/145687102-05c2b191-8369-4622-a79f-4edc414abc0e.png)&nbsp;。<br>

同样根据费马小定律，
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145687996-0d952539-ac13-4593-9ade-ba33c16017da.png)&nbsp;，
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145688007-66b11cc5-8799-4d9a-b68b-7be7e9f0a563.png)&nbsp;要么为1，要么为-1，而
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;要么是二次剩余，要么是二次非剩余，因此，当
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;是模
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的二次非剩余时，有
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145687125-56a02ae5-6134-486b-a99d-c73ac3069003.png)&nbsp;。

## 二、证明
将以&nbsp;![image](https://user-images.githubusercontent.com/23076538/145689112-1a7e3c18-ea5e-4f74-b116-fe8b34933933.png)&nbsp;时进行说明：<br>
![image](https://user-images.githubusercontent.com/23076538/145689193-2bcdcb6c-798d-498d-992c-5569742d67f2.png)<br>
假如0位已被哈希占用，此时触发二次探测再散列，先忽略负值的跳位，有
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145689349-7d6e4c20-f346-48dc-96aa-3fa908bbb1ea.png)&nbsp;，这与二次剩余问题同出一撤，那么什么情况下每次探测的空格不重复呢？<br>

假设存在
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145703866-541955dc-3bbd-4f7b-b83b-26336b472df1.png)&nbsp;，使探测的空格重复，有
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145689814-214b302a-3a9c-4b4d-906f-f63f56f8f5d6.png)&nbsp;，存在以下条件使此等式不成立（反过来说不成立说明不重复）：<br>
> * 要令任意&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;和任意&nbsp;![image](https://user-images.githubusercontent.com/23076538/145703894-9e17317a-6373-44dc-a281-fb77ae594efe.png)&nbsp;，使![image](https://user-images.githubusercontent.com/23076538/145703658-ad5ab0d7-41b4-447e-9019-d37b0ff16527.png)&nbsp;不被&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;整除，首先&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;不能是只包含&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;或&nbsp;![image](https://user-images.githubusercontent.com/23076538/145703894-9e17317a-6373-44dc-a281-fb77ae594efe.png)&nbsp;其中的质因子的合数，由于&nbsp;![image](https://user-images.githubusercontent.com/23076538/145685887-a6469851-0cc8-42ef-b689-fea27d1e45ab.png)&nbsp;和&nbsp;![image](https://user-images.githubusercontent.com/23076538/145703894-9e17317a-6373-44dc-a281-fb77ae594efe.png)&nbsp;是任意的，也即&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;不能是合数，&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;得是质数。
> * 由于![image](https://user-images.githubusercontent.com/23076538/145703481-331034fd-c97e-49ce-9402-1e7b7f598755.png)&nbsp;和&nbsp;![image](https://user-images.githubusercontent.com/23076538/145703489-4c4ca5d2-f62b-4ec6-a8f8-394a986e2500.png)&nbsp;是任意取值的，且&nbsp;![image](https://user-images.githubusercontent.com/23076538/145705641-337641f0-8ec6-4423-8012-437b4abd766f.png)&nbsp;，即符合条件&nbsp;![image](https://user-images.githubusercontent.com/23076538/145705965-8f1058f0-a8ae-4788-8b10-52f8b1f2ac8c.png)&nbsp;即可，因此有&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706020-99c69c90-766f-4e28-b809-c069fcb5c9f4.png)&nbsp;

因此，当&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;为质数，并且增量序列为：
&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706160-88fa3043-f621-4997-b4f1-cbfab9312828.png)&nbsp;时，可以保证探测空格不重复，如上例&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706252-a2f0cf31-f185-484a-8dab-026e3d6f085c.png)&nbsp;时，&nbsp;![image](https://user-images.githubusercontent.com/23076538/146518752-dc72dec6-d749-4340-bcd7-e0823f1c4c33.png)&nbsp;对应二次剩余下标&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706267-282198da-e315-403b-a543-1c7aae1fe4e7.png)&nbsp;。<br>

那么剩下的&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706297-2bdd1ac2-e443-494a-875b-5daa78a3a572.png)&nbsp;呢？其实这些就是&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706252-a2f0cf31-f185-484a-8dab-026e3d6f085c.png)&nbsp;时的二次非剩余。<br>

若&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706550-e08f71f2-f4ad-4c19-b3a2-2ebea21c41ac.png)&nbsp;是&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的二次剩余集合，它们必然是各不相同的，现假设有集合&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706531-838e0891-8661-46ac-828e-4d8641790f58.png)&nbsp;，由于&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686327-b8a7e79e-38aa-45f0-9344-a7d638eacc54.png)&nbsp;之间各不相同，则&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686775-0fd86ceb-d312-4d2d-9419-13019502fa1f.png)&nbsp;必然也各不相同。如此，假若可以令集合&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686327-b8a7e79e-38aa-45f0-9344-a7d638eacc54.png)&nbsp;与集合&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686775-0fd86ceb-d312-4d2d-9419-13019502fa1f.png)&nbsp;没有交集，则它们的并集元素有&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686761-3a674a6d-88be-4874-be90-df075e242475.png)&nbsp;个，也就是等于所有剩余集合。由于集合&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686327-b8a7e79e-38aa-45f0-9344-a7d638eacc54.png)&nbsp;是二次剩余集合，则需找到一个&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;，令集合&nbsp;![image](https://user-images.githubusercontent.com/23076538/145686775-0fd86ceb-d312-4d2d-9419-13019502fa1f.png)&nbsp;等于二次非剩余集合即可。<br>

我们根据欧拉判别法则进行命题转换：当&nbsp;![image](https://user-images.githubusercontent.com/23076538/145687102-05c2b191-8369-4622-a79f-4edc414abc0e.png)&nbsp;时，令&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706885-ed8aaeec-2386-4e8b-b678-9a377adb4b1b.png)&nbsp;即可。<br>

对&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706885-ed8aaeec-2386-4e8b-b678-9a377adb4b1b.png)&nbsp;进行二项展开有：<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/23076538/145707204-37c8ee09-2bb8-4200-bbc0-61d15104fbc6.png)<br>
![image](https://user-images.githubusercontent.com/23076538/145707211-eecfea55-6479-46bf-a2d0-b8336fc7a4f9.png)<br>
![image](https://user-images.githubusercontent.com/23076538/145707235-9f7e48f6-ff23-4691-99d1-dd257964c4e2.png)<br>

从而得到&nbsp;![image](https://user-images.githubusercontent.com/23076538/145707350-8bc8da81-edd5-4803-bc44-33f351363894.png)&nbsp;，根据费马小定律，可得&nbsp;![image](https://user-images.githubusercontent.com/23076538/145707366-8ea6b86b-2adf-469f-aee6-8c63b580c3fc.png)&nbsp;，要使之恒成立，&nbsp;![image](https://user-images.githubusercontent.com/23076538/145707417-b50009c7-53f7-44ca-8465-3aa02b2e9165.png)&nbsp;必须为奇数，即&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;为&nbsp;![image](https://user-images.githubusercontent.com/23076538/145707455-133f4b8e-3827-4f7a-81cf-077484c799d2.png)&nbsp;形式时，有&nbsp;![image](https://user-images.githubusercontent.com/23076538/145707496-013fb990-bfcb-43a7-9e34-30b80cc19a28.png)&nbsp;必为奇数。<br>

因此，当&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;为&nbsp;![image](https://user-images.githubusercontent.com/23076538/145707455-133f4b8e-3827-4f7a-81cf-077484c799d2.png)&nbsp;形式的质数时，集合&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706531-838e0891-8661-46ac-828e-4d8641790f58.png)&nbsp;就是&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;的非剩余集合，也就是说剩余集合与非剩余集合是关于模&nbsp;![image](https://user-images.githubusercontent.com/23076538/145684428-0bb7a272-cc1c-405a-9cd4-e47f2a4d0017.png)&nbsp;对称的。现想象将哈希列表首尾相连形成一个环，从起始点0向逆时针方向移位代表的是正数增位序列&nbsp;![image](https://user-images.githubusercontent.com/23076538/145706160-88fa3043-f621-4997-b4f1-cbfab9312828.png)&nbsp;移位，由于对称，剩下的二次非剩余下标位置，必是顺时针方向的相反意义的二次剩余移位，由于二次剩余和非二次剩余之和为&nbsp;![image](https://user-images.githubusercontent.com/23076538/145710232-d9af3d59-3581-43e1-99be-86b35927d409.png)&nbsp;，加上0位的一格即为哈希表总长度，因此，最终增量序列&nbsp;![image](https://user-images.githubusercontent.com/23076538/145710158-87c74a7a-fa81-41db-95e8-1d3e949b9f4b.png)&nbsp;可以扫描到全表。

## 三、总结

当哈希表长为形如&nbsp;![image](https://user-images.githubusercontent.com/23076538/145710286-96795d2c-a3fb-4831-8cd5-eef08a744047.png)&nbsp;的质数时，移位增量序列&nbsp;![image](https://user-images.githubusercontent.com/23076538/145710158-87c74a7a-fa81-41db-95e8-1d3e949b9f4b.png)&nbsp;可以扫描到全表。
