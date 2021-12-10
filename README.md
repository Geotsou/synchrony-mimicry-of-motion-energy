# synchrony-mimicry-of-motion-energy
Finding synchrony/mimicry of motion energy in dyadic communication

The purpose of this program is to quantify synchrony or mimicry in body motion while two persons having a conversation.
The data that I used was provided by the MAHNOB-Mimicry database[1] and contains many sessions of recorded videos from
dyads having conversation for different topics.

By using OpenPose [2] I could estimate the 2D pose for each participant. To create motion energy time series for each one, 
I calculated the Euclidean distance of each body part between two frames and sum them.

To measure synchrony/mimicry I used Windowed Cross Correlation(WCC) and Convergent Cross Mapping(CCM). With WCC, synchrony/mimicry is measured 
by sliding a window of 180 frames and calculating the cross correlation between the time series with max lag of 90 frames. 
The criterion for synchrony is when the time lag of cross correlation is in range of [0 - 0.2] sec and if the time lag exceeds this range 
then is considered as mimicry. With CCM, I want to investigate if there is casualty between the movements by checking if one shadow manifold 
can be predicted by the other.



[1] https://mahnob-db.eu/mimicry/
[2] Zhe Cao, Gines Hidalgo, Tomas Simon, Shih-En Wei, and Yaser Sheikh. OpenPose: realtime multi-person 2D pose estimation using Part Affinity Fields. In arXiv preprint arXiv:1812.08008,2018.
