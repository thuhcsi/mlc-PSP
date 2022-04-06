---
layout: default
---


# Abstract

For text-to-speech synthesis, prosodic structure prediction (PSP) plays an important role in producing natural and intelligible speech.
Although inter-utterance linguistic information can influence the speech interpretation of the target utterance, previous works on PSP mainly focus on utilizing intra-utterance linguistic information of the current utterance only.
This work proposes to use inter-utterance linguistic information to improve the performance of PSP.
Multi-level contextual information, which includes both inter-utterance and intra-utterance linguistic information, is extracted by a hierarchical encoder from character level, utterance level and discourse level of the input text.
Objective evaluation results on two datasets show that our method achieves better F1 scores, with the best absolute improvement of 0.70%, 1.14% and 1.05% for prosodic word (PW), prosodic phrase (PPH) and intonational phrase (IPH) respectively. 
It demonstrates the effectiveness of using multi-level contextual information for PSP. 
Subjective preference tests also indicate the naturalness of synthesized speeches are improved.

# Demo
To further evaluate the PSP performance of different methods and their impact on text-to-speech synthesis, some synthesized samples are provided for comparision. 
Speeches provided were generated using Huya TTS toolkit which is based on DurIAN and HiFi-GAN.
In each table cell, the first line is the Chinese character sequence with prosodic boundary labels inserted and the second line is the corresponding synthesized speech. 
There are three kinds of prosodic boundary labels: **#1** indicates that there's a prosodic word boundary after the preceding Chinese character, **#2** indicates that there's a prosodic phrase boundary and **#3** indicates an intonational phrase boundary.

## Comparison Between Proposed and BLSTM-CRF
In the following table, 10 synthesized sample pairs are provided.
**Proposed** means the prosodic structure is predicted by our proposed method and **BLSTM-CRF** means the prosodic structure is predicted by baseline model BLSTM-CRF. 
<table>
    <thead>
        <tr>
            <th>

            </th>
            <th>
                Proposed
            </th>
            <th>
                BLSTM-CRF
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                1
            </td>
            <td>
                <p>三十四名#1被#1刷下来的#1旗丁#3哭天抹泪地#1走了,汪半城的#1心里#2很不是#1滋味。</p>
                <p>Thirty four villagers who was not selected walked away in tears, which made Bancheng Wang upset.</p>
                <div>
                    <audio src='demo/proposed.33.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>三十四名#1被刷下来的#1旗丁#1哭天抹泪地#1走了,汪半城的#1心里#1很#1不是#1滋味。</p>
                <p>Thirty four villagers who was not selected walked away in tears, which made Bancheng Wang upset.</p>
                <div>
                    <audio src='demo/blstm_crf.33.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                2
            </td>
            <td>
                <p>幺蛾子#3是#1方言,就是#1耍花招,出鬼点子,出#1馊主意,歪门邪道的#1意思。</p>
                <p>Yaoezi in dialect means playing tricks or coming up with bad ideas. </p>
                <div>
                    <audio src='demo/proposed.71.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>幺蛾子#1是#1方言,就是#1耍花招,出鬼点子,出馊主意,歪门邪道的#1意思。</p>
                <p>Yaoezi in dialect means playing tricks or coming up with bad ideas. </p>
                <div>
                    <audio src='demo/blstm_crf.71.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                3
            </td>
            <td>
                <p>右屯的#1屯丁#2来自#1吉林,不堪#1苦作#3逃跑了#1二三百人,又#1抽丁#1补充#1中屯#1几百人,缺口#1只好#1由#1盛京来的#1余丁#1补充。</p>
                <p>Farming was so tiring that more than two hundred Youtun villagers from Jilin escaped. Several hundreds villagers were sent to Zhongtun. The last villagers were from Shengjin. </p>
                <div>
                    <audio src='demo/proposed.112.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>右屯的#1屯丁#1来自#1吉林,#3不堪#1苦作#2逃跑了#1二三百人,#3又#1抽丁#1补充#1中屯#1几百人,#3缺口#2只好#1由#1盛京#1来的#1余丁#1补充。 </p>
                <p>Farming was so tiring that more than two hundred Youtun villagers from Jilin escaped. Several hundreds villagers were sent to Zhongtun. The last of villagers were from Shengjin. </p>
                <div>
                    <audio src='demo/blstm_crf.112.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                4
            </td>
            <td>
                <p>嗯#3你们#1不#1实心#1任事,督促#1屯丁;屯丁#1不知#1感念#1天恩,勤劳#1生产,开荒#1种地,却#1好逸恶劳,自暴自弃,甘心#1冻饿。</p>
                <p>Well, you didn't work hard and supervise villagers. Lazy villagers didn't work hard, appreciate the grace of emperor, works diligently, or cultivates the wasteland, but they like leisure and hates labor, giving up on themselves, and suffered from hunger.</p>
                <div>
                    <audio src='demo/proposed.140.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>嗯你们#1不#1实心#1任事,督促#1屯丁;屯丁#1不知#1感念#1天恩,勤劳#1生产,开荒种地,却#1好逸恶劳,自暴自弃,甘心#1冻饿。</p>
                <p>Well, you didn't work hard and supervise villagers. Lazy villagers didn't work hard, appreciate the grace of emperor, works diligently, or cultivates the wasteland, but they like leisure and hates labor, giving up on themselves, and suffered from hunger.</p>
                <div>
                    <audio src='demo/blstm_crf.140.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                5
            </td>
            <td>
                <p>余老举人#1扑哧#1一下#1就笑了,一是#1有了#1呲脚的#1台阶了,再者#1细想#3也#1真是#1没意思。</p>
                <p>Mr. Yu burst into laughter. His face was saved and he would not care about it anymore.</p>
                <div>
                    <audio src='demo/proposed.330.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>余老举人#1扑哧#1一下#1就#1笑了,一是#1有了#1呲脚的#1台阶了,再者#1细想#1也#1真是#1没意思。</p>
                <p>Mr. Yu burst into laughter. His face was saved and he would not care about it anymore.</p>
                <div>
                    <audio src='demo/blstm_crf.330.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                6
            </td>
            <td>
                <p>五爷#1也是#1第一回#1和#1桃儿#1见面,当年#1桃儿#1逃走的#1时候的#1背影#3还#1历历在目。</p>
                <p>Wuye met Taoer for the first time, but he still remembered the moment when Taoer escaped.</p>
                <div>
                    <audio src='demo/proposed.504.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>五爷#1也是#1第一回#1和#1桃儿#1见面,当年#1桃儿#1逃走的#1时候的#1背影#1还#1历历在目。</p>
                <p>Wuye met Taoer for the first time, but he still remembered the moment when Taoer escaped.</p>
                <div>
                    <audio src='demo/blstm_crf.504.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                7
            </td>
            <td>
                <p>图敏#1半晌#1没言语,叹了口气#3告诉#1汪半城:唉呀#3桃儿啊#1是个#1好格格,她的命#3是#1穆隆#1阿救的。</p>
                <p>Tuming kept silent for a while. Then he sighed and said to Bancheng Wang "Taoer is a good girl. Mulonga saved her life."</p>
                <div>
                    <audio src='demo/proposed.532.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>图敏#1半晌#1没言语,叹了口气#1告诉#1汪半城:唉呀#3桃儿啊#1是个#1好格格,她的#1命#2是#1穆隆阿救的。</p>
                <p>Tuming kept silent for a while. Then he sighed and said to Bancheng Wang "Taoer is a good girl. Mulonga saved her life."</p>
                <div>
                    <audio src='demo/blstm_crf.532.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                8
            </td>
            <td>
                <p>前郭尔罗斯#3距离#1古城子#1路途#1遥远,图敏#1出面,安排#1包家#1送亲的#1陪着#1新娘,住在#1城里的#1客栈。</p>
                <p>Qianguoerluosi was distant from Guchengzi. Tuming sent bride and her relatives to live in a inn.</p>
                <div>
                    <audio src='demo/proposed.628.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>前郭尔罗斯#3距离#1古城子#1路途#1遥远,图敏#1出面,安排#1包家#1送亲的#3陪着#1新娘,住在#1城里的#1客栈。</p>
                <p>Qianguoerluosi was distant from Guchengzi. Tuming sent bride and her relatives to live in a inn.</p>
                <div>
                    <audio src='demo/blstm_crf.628.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                9
            </td>
            <td>
                <p>要求#1屯丁#1十户#1联保,吉林#1屯丁#1每丁#2必须#1保质#1保量#1开荒#1一垧半,盛京#1屯丁#1两垧,京旗#1自便。</p>
                <p>It was required that ten families must supervise each other. Villagers from Jilin must farm one and a half shang. Villagers from Shengjin must farm two shang but villagers from Jinqi had no requirement.</p>
                <div>
                    <audio src='demo/proposed.722.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>要求#1屯丁#1十户#1联保,吉林#1屯丁#1每丁#2必须#1保质#1保量#3开荒#1一垧半,盛京#1屯丁#1两垧,京旗#1自便。</p>
                <p>It was required that ten families must supervise each other. Villagers from Jilin must farm one and a half shang. Villagers from Shengjin must farm two shang but villagers from Jinqi had no requirement.</p>
                <div>
                    <audio src='demo/blstm_crf.722.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                10
            </td>
            <td>
                <p>载钦#3也在#1中屯#1镶黄旗#1头屯#1忙着,作为#1京旗#1佐领,在#1田间#3督励#1京旗#1种地。</p>
                <p>Zaiqin was busy working in Zhongtun. As the leader of Jinqi, he was supervising villagers from Jinqi farming.</p>
                <div>
                    <audio src='demo/proposed.749.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>载钦#2也#1在#1中屯#1镶黄旗头屯#1忙着,作为#1京旗#1佐领,在#1田间#1督励#1京旗#1种地。</p>
                <p>Zaiqin was busy working in Zhongtun. As the leader of Jinqi, he was supervising villagers from Jinqi farming.</p>
                <div>
                    <audio src='demo/blstm_crf.749.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
    </tbody>
</table>

## Comparison Between Proposed and Transformer
In the following table, 10 synthesized sample pairs are provided.
**Proposed** means the prosodic structure is predicted by our proposed method and **Transformer** means the prosodic structure is predicted by baseline model Transformer.
<table>
    <thead>
        <tr>
            <th>

            </th>
            <th>
                Proposed
            </th>
            <th>
                Transformer
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                1
            </td>
            <td>
                <p>他#1扭头#1对#1载钦说:笔帖式,你把#1他们的#1花名册#1要过来,和#1富征额#1一起#1挨个#1核对,凡是#1年逾#1五十岁的、不堪#1垦种的,一律#1给我#1辞退。</p>
                <p>He said to Zaiqin "Bitieshi, give me their names and check it with Fuzhenge. Everyone whose age is greater than fifty and can't bear farming will be fired!"</p>
                <div>
                    <audio src='demo/proposed.28.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>他扭头#1对#1载钦说:笔帖式,你#1把#1他们的#1花名册#3要过来,和#1富征额#1一起#1挨个#1核对,凡是#1年逾#1五十岁的、不堪#1垦种的,一律#1给我#1辞退。</p>
                <p>He said to Zaiqin "Bitieshi, give me their names and check it with Fuzhenge. Everyone whose age is greater than fifty and can't bear farming will be fired!"</p>
                <div>
                    <audio src='demo/transformer.28.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                2
            </td>
            <td>
                <p>吉林#1将军#1衙门#1下发#1文书,任命#1图敏#3为#1左屯#1左翼#1佐领,汪半城#3为#1左屯#1右翼#1佐领。</p>
                <p>The general of Jilin appointed Tuming as the leader of Zuotun and appointed Bancheng Wang as the leader of Youtun.</p>
                <div>
                    <audio src='demo/proposed.101.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>吉林#1将军#1衙门#1下发#1文书,任命#1图敏为#1左屯#1左翼#1佐领,汪半城#1为#1左屯#1右翼#1佐领。</p>
                <p>The general of Jilin appointed Tuming as the leader of Zuotun and appointed Bancheng Wang as the leader of Youtun.</p>
                <div>
                    <audio src='demo/transformer.101.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                3
            </td>
            <td>
                <p>阿尔喀善#1接过了#1话茬:呃#3下官#1倒有个#1办法,富老#1将军#1来视察#3就#1领着#1去#1左屯。</p>
                <p>Aerkashan said "I have an idea. When the old general visit us, we can lead him to Zuotun.</p>
                <div>
                    <audio src='demo/proposed.220.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>阿尔喀善#1接过了#1话茬:呃#3下官#1倒有个#1办法,富老将军#1来视察#1就领着#1去#1左屯。</p>
                <p>Aerkashan said "I have an idea. When the old general visit us, we can lead him to Zuotun.</p>
                <div>
                    <audio src='demo/transformer.220.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                4
            </td>
            <td>
                <p>十天#1之后,粟末#1书院#1开讲了,窦心传#3应#1黄五爷#1之邀#3主讲#1第一课#3古城子#1历史。</p>
                <p>Ten days after, Sumo School was started. Huangwuye invited Chuanxin Dou to talk about the history of Guchengzi.</p>
                <div>
                    <audio src='demo/proposed.314.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>十天#1之后,粟末#1书院#2开讲了,窦心传#3应#1黄五爷#1之邀#3主讲#1第一课#1古城子#1历史。</p>
                <p>Ten days after, Sumo School was started. Huangwuye invited Chuanxin Dou to talk about the history of Guchengzi.</p>
                <div>
                    <audio src='demo/transformer.314.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                5
            </td>
            <td>
                <p>拉林河#1两岸#3能#1傍上#1点边的#1文化人#3基本上#1悉数#1到场了,场面#1庄重#1热烈。</p>
                <p>Almost all people who lived around Laling River and had studied in school presented. It was a solemn and enthusiastic scene.</p>
                <div>
                    <audio src='demo/proposed.315.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>拉林河#1两岸#1能#1傍上#1点边的#1文化人#1基本上#1悉数#1到场了,场面#1庄重#1热烈。</p>
                <p>Almost all people who lived around Laling River and had studied in school presented. It was a solemn and enthusiastic scene.</p>
                <div>
                    <audio src='demo/transformer.315.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                6
            </td>
            <td>
                <p>汪半城#1觉得#1媳妇#1不对劲,原来的#1痴症#3这两天#1不药#1而愈了,就是#1动不动#1就#1流眼泪呀。</p>
                <p>Bancheng Wang found there was something wrong with his wife. Although she no longer seemed to be stupid, she was crying all the time.</p>
                <div>
                    <audio src='demo/proposed.529.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>汪半城#1觉得#1媳妇#1不对劲,原来的#1痴症#1这两天#1不药#1而愈了,就是#1动不动#1就#1流眼泪呀。</p>
                <p>Bancheng Wang found there was something wrong with his wife. Although she no longer seemed to be stupid, she was crying all the time.</p>
                <div>
                    <audio src='demo/transformer.529.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                7
            </td>
            <td>
                <p>双录#1提醒他:叔,您老#1可#1别忘了,待会啊#3您得去给#1黄五爷#1书院#1剪彩呀。</p>
                <p>Shuanglu noticed him "My uncle, don't forget to present the ceremony celebrating for the school of Huangwuye."</p>
                <div>
                    <audio src='demo/proposed.285.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>双录#1提醒他:叔,您老#1可#1别忘了,待会啊#1您得去#1给#1黄五爷#1书院#1剪彩呀。</p>
                <p>Shuanglu noticed him "My uncle, don't forget to present the ceremony celebrating for the school of Huangwuye."</p>
                <div>
                    <audio src='demo/transformer.285.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                8
            </td>
            <td>
                <p>蓼花才#1十九岁,在#1哥嫂的#1哄劝#1逼迫#1之下#3同意了#1这门#1婚事,心里#1委屈,眼泪#1掉个#1不停。</p>
                <p>Luhua was nineteen years old. She agreed her marriage under the pressure and persuasion of her brother and her sister-in-law. She felt aggrieved and burst into tears.</p>
                <div>
                    <audio src='demo/proposed.893.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>蓼花才#1十九岁,在#1哥嫂的#1哄劝#1逼迫之下#1同意了#1这门#1婚事,心里#1委屈,眼泪#1掉个#1不停。</p>
                <p>Luhua was nineteen years old. She agreed her marriage under the pressure and persuasion of her brother and her sister-in-law. She felt aggrieved and burst into tears.</p>
                <div>
                    <audio src='demo/transformer.893.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                9
            </td>
            <td>
                <p>三十四名#1被#1刷下来的#1旗丁#3哭天抹泪地#1走了,汪半城的#1心里#2很不是#1滋味。</p>
                <p>Thirty four villagers who was not selected walked away in tears, which made Bancheng Wang upset.</p>
                <div>
                    <audio src='demo/proposed.33.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>三十四名#1被#1刷下来的#1旗丁#1哭天抹泪地#1走了,汪半城的#1心里#1很不是#1滋味。</p>
                <p>Thirty four villagers who was not selected walked away in tears, which made Bancheng Wang upset.</p>
                <div>
                    <audio src='demo/transformer.33.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                10
            </td>
            <td>
                <p>心乱如麻的#1桃儿#3乐不得#1早早的#1离开这#1是非#1之地,张罗着#1收拾#1东西,上了#1牛车#1走人了。</p>
                <p>Taoer was so anxious that she was willing to leave as soon as possible. She packed up her things and went away by cattle. </p>
                <div>
                    <audio src='demo/proposed.79.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>心乱如麻的#1桃儿#1乐不得#1早早的#1离开#1这#1是非之地,张罗着#1收拾#1东西,上了#1牛车#1走人了。</p>
                <p>Taoer was so anxious that she was willing to leave as soon as possible. She packed up her things and went away by cattle. </p>
                <div>
                    <audio src='demo/transformer.79.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
    </tbody>
</table>
