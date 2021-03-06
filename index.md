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
                <p>????????????#1???#1????????????#1??????#3???????????????#1??????,????????????#1??????#2?????????#1?????????</p>
                <p>Thirty four villagers walked away in tears, which made Bancheng Wang upset.</p>
                <div>
                    <audio src='demo/proposed.33.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>????????????#1???????????????#1??????#1???????????????#1??????,????????????#1??????#1???#1??????#1?????????</p>
                <p>Thirty four villagers walked away in tears, which made Bancheng Wang upset.</p>
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
                <p>?????????#3???#1??????,??????#1?????????,????????????,???#1?????????,???????????????#1?????????</p>
                <p>Yaoezi in dialect means playing tricks or coming up with bad ideas. </p>
                <div>
                    <audio src='demo/proposed.71.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>?????????#1???#1??????,??????#1?????????,????????????,????????????,???????????????#1?????????</p>
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
                <p>?????????#1??????#2??????#1??????,??????#1??????#3?????????#1????????????,???#1??????#1??????#1??????#1?????????,??????#1??????#1???#1????????????#1??????#1?????????</p>
                <p>Farming was so tiring that more than two hundred Youtun villagers from Jilin escaped. Several hundreds villagers were sent to Zhongtun. The last villagers were from Shengjin. </p>
                <div>
                    <audio src='demo/proposed.112.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>?????????#1??????#1??????#1??????,#3??????#1??????#2?????????#1????????????,#3???#1??????#1??????#1??????#1?????????,#3??????#2??????#1???#1??????#1??????#1??????#1????????? </p>
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
                <p>???#3??????#1???#1??????#1??????,??????#1??????;??????#1??????#1??????#1??????,??????#1??????,??????#1??????,???#1????????????,????????????,??????#1?????????</p>
                <p>Well, you didn't work hard and supervise villagers. Lazy villagers didn't work hard, appreciate the grace of emperor, works diligently, or cultivates the wasteland, but they like leisure and hates labor, giving up on themselves, and suffered from hunger.</p>
                <div>
                    <audio src='demo/proposed.140.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>?????????#1???#1??????#1??????,??????#1??????;??????#1??????#1??????#1??????,??????#1??????,????????????,???#1????????????,????????????,??????#1?????????</p>
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
                <p>????????????#1??????#1??????#1?????????,??????#1??????#1?????????#1?????????,??????#1??????#3???#1??????#1????????????</p>
                <p>Mr. Yu burst into laughter. His face was saved and he would not care about it anymore.</p>
                <div>
                    <audio src='demo/proposed.330.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>????????????#1??????#1??????#1???#1??????,??????#1??????#1?????????#1?????????,??????#1??????#1???#1??????#1????????????</p>
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
                <p>??????#1??????#1?????????#1???#1??????#1??????,??????#1??????#1?????????#1?????????#1??????#3???#1???????????????</p>
                <p>Wuye met Taoer for the first time, but he still remembered the moment when Taoer escaped.</p>
                <div>
                    <audio src='demo/proposed.504.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>??????#1??????#1?????????#1???#1??????#1??????,??????#1??????#1?????????#1?????????#1??????#1???#1???????????????</p>
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
                <p>??????#1??????#1?????????,????????????#3??????#1?????????:??????#3?????????#1??????#1?????????,?????????#3???#1??????#1????????????</p>
                <p>Tuming kept silent for a while. Then he sighed and said to Bancheng Wang "Taoer is a good girl. Mulonga saved her life."</p>
                <div>
                    <audio src='demo/proposed.532.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>??????#1??????#1?????????,????????????#1??????#1?????????:??????#3?????????#1??????#1?????????,??????#1???#2???#1??????????????????</p>
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
                <p>???????????????#3??????#1?????????#1??????#1??????,??????#1??????,??????#1??????#1?????????#1??????#1??????,??????#1?????????#1?????????</p>
                <p>Qianguoerluosi was distant from Guchengzi. Tuming sent bride and her relatives to live in a inn.</p>
                <div>
                    <audio src='demo/proposed.628.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>???????????????#3??????#1?????????#1??????#1??????,??????#1??????,??????#1??????#1?????????#3??????#1??????,??????#1?????????#1?????????</p>
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
                <p>??????#1??????#1??????#1??????,??????#1??????#1??????#2??????#1??????#1??????#1??????#1?????????,??????#1??????#1??????,??????#1?????????</p>
                <p>It was required that ten families must supervise each other. Villagers from Jilin must farm one and a half shang. Villagers from Shengjin must farm two shang but villagers from Jinqi had no requirement.</p>
                <div>
                    <audio src='demo/proposed.722.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>??????#1??????#1??????#1??????,??????#1??????#1??????#2??????#1??????#1??????#3??????#1?????????,??????#1??????#1??????,??????#1?????????</p>
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
                <p>??????#3??????#1??????#1?????????#1??????#1??????,??????#1??????#1??????,???#1??????#3??????#1??????#1?????????</p>
                <p>Zaiqin was busy working in Zhongtun. As the leader of Jinqi, he was supervising villagers from Jinqi farming.</p>
                <div>
                    <audio src='demo/proposed.749.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>??????#2???#1???#1??????#1???????????????#1??????,??????#1??????#1??????,???#1??????#1??????#1??????#1?????????</p>
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
                <p>???#1??????#1???#1?????????:?????????,??????#1?????????#1?????????#1?????????,???#1?????????#1??????#1??????#1??????,??????#1??????#1?????????????????????#1?????????,??????#1??????#1?????????</p>
                <p>He said to Zaiqin "Bitieshi, give me their names and check it with Fuzhenge. Everyone whose age is greater than fifty and can't bear farming will be fired!"</p>
                <div>
                    <audio src='demo/proposed.28.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>?????????#1???#1?????????:?????????,???#1???#1?????????#1?????????#3?????????,???#1?????????#1??????#1??????#1??????,??????#1??????#1?????????????????????#1?????????,??????#1??????#1?????????</p>
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
                <p>??????#1??????#1??????#1??????#1??????,??????#1??????#3???#1??????#1??????#1??????,?????????#3???#1??????#1??????#1?????????</p>
                <p>The general of Jilin appointed Tuming as the leader of Zuotun and appointed Bancheng Wang as the leader of Youtun.</p>
                <div>
                    <audio src='demo/proposed.101.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>??????#1??????#1??????#1??????#1??????,??????#1?????????#1??????#1??????#1??????,?????????#1???#1??????#1??????#1?????????</p>
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
                <p>????????????#1?????????#1??????:???#3??????#1?????????#1??????,??????#1??????#1?????????#3???#1??????#1???#1?????????</p>
                <p>Aerkasha said "I have an idea. When the old general visit us, we can lead him to Zuotun.</p>
                <div>
                    <audio src='demo/proposed.220.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>????????????#1?????????#1??????:???#3??????#1?????????#1??????,????????????#1?????????#1?????????#1???#1?????????</p>
                <p>Aerkasha said "I have an idea. When the old general visit us, we can lead him to Zuotun.</p>
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
                <p>??????#1??????,??????#1??????#1?????????,?????????#3???#1?????????#1??????#3??????#1?????????#3?????????#1?????????</p>
                <p>Ten days after, Sumo School was started. Huangwuye invited Chuanxin Dou to talk about the history of Guchengzi.</p>
                <div>
                    <audio src='demo/proposed.314.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>??????#1??????,??????#1??????#2?????????,?????????#3???#1?????????#1??????#3??????#1?????????#1?????????#1?????????</p>
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
                <p>?????????#1??????#3???#1??????#1?????????#1?????????#3?????????#1??????#1?????????,??????#1??????#1?????????</p>
                <p>Almost all people who lived around Laling River and had studied in school presented. It was a solemn and enthusiastic scene.</p>
                <div>
                    <audio src='demo/proposed.315.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>?????????#1??????#1???#1??????#1?????????#1?????????#1?????????#1??????#1?????????,??????#1??????#1?????????</p>
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
                <p>?????????#1??????#1??????#1?????????,?????????#1??????#3?????????#1??????#1?????????,??????#1?????????#1???#1???????????????</p>
                <p>Bancheng Wang found there was something wrong with his wife. Although she no longer seemed to be stupid, she was crying all the time.</p>
                <div>
                    <audio src='demo/proposed.529.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>?????????#1??????#1??????#1?????????,?????????#1??????#1?????????#1??????#1?????????,??????#1?????????#1???#1???????????????</p>
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
                <p>??????#1?????????:???,??????#1???#1?????????,?????????#3????????????#1?????????#1??????#1????????????</p>
                <p>Shuanglu noticed him "My uncle, don't forget to present the ceremony celebrating for the school of Huangwuye."</p>
                <div>
                    <audio src='demo/proposed.285.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>??????#1?????????:???,??????#1???#1?????????,?????????#1?????????#1???#1?????????#1??????#1????????????</p>
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
                <p>?????????#1?????????,???#1?????????#1??????#1??????#1??????#3?????????#1??????#1??????,??????#1??????,??????#1??????#1?????????</p>
                <p>Luhua was nineteen years old. She agreed her marriage under the pressure and persuasion of her brother and her sister-in-law. She felt aggrieved and burst into tears.</p>
                <div>
                    <audio src='demo/proposed.893.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>?????????#1?????????,???#1?????????#1??????#1????????????#1?????????#1??????#1??????,??????#1??????,??????#1??????#1?????????</p>
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
                <p>????????????#1???#1????????????#1??????#3???????????????#1??????,????????????#1??????#2?????????#1?????????</p>
                <p>Thirty four villagers walked away in tears, which made Bancheng Wang upset.</p>
                <div>
                    <audio src='demo/proposed.33.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>????????????#1???#1????????????#1??????#1???????????????#1??????,????????????#1??????#1?????????#1?????????</p>
                <p>Thirty four villagers walked away in tears, which made Bancheng Wang upset.</p>
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
                <p>???????????????#1??????#3?????????#1?????????#1?????????#1??????#1??????,?????????#1??????#1??????,??????#1??????#1????????????</p>
                <p>Taoer was so anxious that she was willing to leave as soon as possible. She packed up her things and went away by cattle. </p>
                <div>
                    <audio src='demo/proposed.79.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
            <td>
                <p>???????????????#1??????#1?????????#1?????????#1??????#1???#1????????????,?????????#1??????#1??????,??????#1??????#1????????????</p>
                <p>Taoer was so anxious that she was willing to leave as soon as possible. She packed up her things and went away by cattle. </p>
                <div>
                    <audio src='demo/transformer.79.wav' controls>Your browser does not support the audio element.</audio>
                </div>
            </td>
        </tr>
    </tbody>
</table>
