# Inter-Symbol-Interference-due-to-multi-path-channels
In this part, we consider another form of ISI that happens in channels that we face in wireless communication 
systems. The channel considered here is referred to as the multipath channel.
In wireless channels, signals are transmitted via electromagnetic waves which propagate through the air until 
it reaches the receiver. However, the nature of electromagnetic waves allow that multiple copies of the signal 
would travel around and reach the receiver at different times, such as is shown in Figure 3. This effect is what 
is known as the multipath effect. As is shown in the figure, a symbol transmitted by the transmitter would 
traverse multiple paths until it reaches the receiver. Therefore, the receiver is expected to receiver multiple 
copies of the same transmitted signal. Each of these copies would arrive at a different time (based on how 
long the path that the signal travelled through is) and with a different magnitude (based on how much 
attenuation that the signal suffered from during the transmission across the path). 
This behavior of receiving multiple copies of the same signal is mathematically captured as follows. Let the 
first symbol transmitted by the transmitter be labeled as 𝑥[0]. Then, the receiver would receive a first copy of 
that symbol as
𝑦[0] = ℎ0𝑥[0] + 𝑛[0]
where 𝑦[0] is the received signal, ℎ0 is the channel effect of the first path on the transmitted signal 𝑥[0], and 
𝑛[0] is the noise component.
Now let 𝑥[1] be the second symbol transmitted by the transmitter. Ideally, the receiver would receive a 
signal 𝑦[1] which corresponds to this signal (plus noise). However, the effect of multipath is that 𝑦[1] will 
also include a copy of 𝑥[0] which have passed through a longer path and therefore have arrived at a delayed 
time. Therefore, the second received signal can be written as 
𝑦[1] = ℎ0𝑥[1] + ℎ1𝑥[0] + 𝑛[1]
where ℎ1 is the channel effect of the second path on the transmitted signal. Note that we assume here that 
any symbol which travels through a particular path would have the same channel effect. 
Assume we have a total of 𝐿 paths in our channel. Then, the 𝐿th received signal can be expressed as
𝑦[𝐿 − 1] = ℎ0𝑥[𝐿 − 1] + ℎ1𝑥[𝐿 − 2] + ℎ2𝑥[𝐿 − 3] + ⋯ + ℎ𝐿−2𝑥[1] + ℎ𝐿−1 𝑥[0] + 𝑛[𝐿 − 1]
where ℎ𝑖 corresponds to the channel effect of the (𝑖 + 1)th path, and 𝑥[𝑖] is the (𝑖 + 1)th transmitted 
symbol. 
So this set of equations results in the simple matrix equation 𝑌 = 𝐻𝑋 + 𝑁. From the receiver perspective, 
the terms of the equation are as follows:
1. The transmitted signal is 𝑋. This is what the receiver wants to know or estimate.
2. The received signal is 𝑌. This is what the receiver measures from the channel, and is the main 
observation from which the receiver can figure out what 𝑋 is.
3. The noise component 𝑁. This corresponds to the AWGN noise which corrupts 𝑌
4. The channel coefficients 𝐻. This term captures the effect of the channel on the transmitted symbols 
passing through different paths. There are mechanisms which allow the receiver to estimate the 
value of 𝐻. So we can safely assume that 𝐻 is known at the receiver.
