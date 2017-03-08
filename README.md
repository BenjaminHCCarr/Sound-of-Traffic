# Sound of Traffic
---
201703 Trying to get this to run on OSX, sadly it appears that the problem is an old one with the `JComboBox` which in and of itself seemed to throw this error regularly back in thhe day… see: https://netbeans.org/bugzilla/show_bug.cgi?id=154014

I have sorted the issued down to:
Being in https://github.com/BenjaminHCCarr/Sound-of-Traffic/blob/master/Auralizer.java
likely one of these three lines:
https://github.com/BenjaminHCCarr/Sound-of-Traffic/blob/master/Auralizer.java#L211
https://github.com/BenjaminHCCarr/Sound-of-Traffic/blob/master/Auralizer.java#L153
https://github.com/BenjaminHCCarr/Sound-of-Traffic/blob/master/Auralizer.java#L61

`tee` logging output is in file: https://github.com/BenjaminHCCarr/Sound-of-Traffic/blob/master/SoundOfTraffic.debug.txt

---
**Note** this was written way back in 2004/2005 and requires `tcpdump` to be
installed.  I have not looked at the code since then. Also, super user/root
access is required to get the network data.

Sound of Traffic is a Java "application" which converts TCP/IP header
information into midi notes via the Java Synthesizer. The purpose is to listen
in on network traffic in ordered time, via a tempo, rather than realtime, which
could be more chaotic. In this sense it becomes closer to music then noise.

Play back of traffic is sorted by source and destination addresses and ports.
Ports are assigned individual midi instruments and played on odd or even ticks
depending upon whether it is a source or destination packet. The note played by
the port is based upon the number of hits (amount of traffic) occurring on the
port.

Download and learn more http://www.smokinggun.com/projects/soundoftraffic/
