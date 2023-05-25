# Review Questions

## Kapitel 1

1. Was versteht man unter Safety, was unter Security?

   * Safety: Sicherheit vor Ausfall
   * Security: Schutz vor unautorisiertem Zugriff, etwa auf private Informationen

2. Geben Sie Beispiele!

   * Safety: Backups, Checksummen
   * Security: Verschlüsselung, Anti-Virus

3. Nennen Sie die sieben Ziele der Netzwerksicherheit, die Sie in der Schule kennengelernt haben, und erläutern Sie diese!

   1. Vertraulichkeit: Schutz von Informationen vor unbefugtem Zugriff oder Offenlegung. Dies beinhaltet die Verschlüsselung von Daten und die Implementierung von Zugriffskontrollmechanismen.
   2. Integrität: Sicherstellen, dass Daten während der Übertragung oder Speicherung nicht unbemerkt verändert oder manipuliert werden. Hierbei kommen Integritätsprüfungen, wie beispielsweise kryptografische Hash-Funktionen, zum Einsatz.
   3. Verfügbarkeit: Gewährleistung, dass Netzwerkdienste und -ressourcen zuverlässig und kontinuierlich verfügbar sind. Dazu gehören Maßnahmen zur Verhinderung von Ausfällen, DDoS-Schutz (Distributed Denial of Service) und die Implementierung von Notfallwiederherstellungsplänen.
   4. Authentifizierung: Überprüfung der Identität von Benutzern, Geräten oder Systemen, um sicherzustellen, dass nur autorisierte Personen oder Entitäten auf das Netzwerk zugreifen können. Dies kann durch Passwörter, biometrische Merkmale oder andere Authentifizierungsmethoden erfolgen.
   5. Autorisierung: Bestimmung der Zugriffsrechte und Berechtigungen für authentifizierte Benutzer. Dadurch wird sichergestellt, dass Benutzer nur auf die ihnen zugewiesenen Ressourcen zugreifen können.
   6. Verfügbarkeit: Schutz des Netzwerks und der Ressourcen vor Bedrohungen wie Viren, Malware, Würmern oder Hackern. Dies erfordert die Implementierung von Sicherheitsmechanismen wie Firewalls, Intrusion-Detection-Systemen und Antivirenprogrammen.
   7. Überwachung und Protokollierung: Kontinuierliche Überwachung des Netzwerks, um Sicherheitsvorfälle zu erkennen und darauf zu reagieren. Die Protokollierung von Netzwerkaktivitäten ermöglicht eine spätere Analyse von Sicherheitsvorfällen und unterstützt forensische Untersuchungen.

4. Was besagt Kerckhoff’s Principle?

    Die Sicherheit eines Systems sollte nicht auf der Geheimhaltung des Systems, sondern der des Schlüssels obliegen. Der Gegner soll das System kennen.

5. Was wäre das Gegenteil davon?

    Wenn das System nur als sicher betrachtet wird, weil es versteckt ist.

6. Was besagt Scheier’s Law?

    Jeder kann eine Verschlüsselung entwickelt, die man selbst nicht knacken kann. Das bedeutet nicht, dass diese sicher ist. Ein solcher Verschlüsselungsalgorithmus sollte öffentlich sein und von Experten überprüft werden.

7. Was folgt daraus für Sicherheitalgorithmen in Software?

    Die Folge daraus ist, dass keine eigenen Algorithmen entwickelt, sondern bestehende verwendet werden sollten, die schon überprüft wurden.

8. Was ist ein Attacker Model?

   * Umgebung des Angreifers
   * Potenzial für den Angreifer
   * Vorteile für den Angreifer

9. Wozu wird ein Attacker Model benötigt?

    Ein _Attacker Model_ wird benötigt, um die Sicherheit von interaktiven Protokollen zu bestimmen. Man analysiert, welche Möglichkeiten ein Angreifer hat die Verschlüsselung zu knacken, wenn ihm bestimmte Möglichkeiten gegeben werden.

10. Was ist das Dolev-Yao Attacker Model? Wozu ist demnach ein Angreifer in der Lage?

        Im Dolev-Yao Attacker Model geht man von bestimmten Bedingungen und einer bestimmten Umgebung aus, in denen sich ein Angreifer befindet, um die Verschlüsselung eines Protokolls zu knacken:

            1. Umgebung: ein Netzwerk, das aus einer bestimmten Anzahl an Teilnehmern besteht. Alle Teilnehmer sind miteinander vernetzt und tauschen Nachrichten aus. Weitere Teilnehmer können zu jedem Zeitpunkt dazukommen und müssen nicht autorisiert sein.
            2. Angreifer: der Angreifer ist ein Teilnehmer des Netzwerks, der Nachrichten senden, empfangen, abfangen und manipulieren und als ein anderer Teilnehmer senden kann. Der Angreifer kann nicht die Sicherheit knacken.

        Ein Protokoll kann nach diesem Angreifermodell als sicher betrachtet werden, wenn der Angreifer keine Nachrichten 1.1.unentdeckt1.1. manipulieren kann.

11. Wofür stehen Alice, Bob, Trudy und Eve in der Literatur?

            1. Alice und Bob: normale Gesprächspartner, die sicher Nachrichten austauschen wollen.
            2. Trudy: steht für Intruder und kann Nachrichten abfangen, löschen und hinzufügen.
            3. Eve: steht für Eavesdropper und kann Nachrichten (passiv) mitlesen.

12. Was sind entsprechende Entitäten in der Realität?

            1. Alice und Bob: Webbrowser/Server, Client/Server, DNS-Server, Router
            2. Trudy und Eve: Angreifer, die eine Verschlüsselung knacken wollen

13. Erklären Sie Verschlüsselung formal mithilfe von Funktionen und erklären Sie die verwendeten
    Parameter!

        $E(K_{e}, m) = c$

            1. $E$ ist die Verschlüsselungsfunktion
            2. $K$ ist der Schlüssel. Man unterscheidet zwischen symmetrischer $K_{e} = K_{d}$ und asymmetrischer Verschlüsselung, bei der zwei Schlüssel gibt, für die meist $K_{e} = K^{+}$ und $K_{d} = K^{-}$ gilt.
            3. $m$ ist die Klartextnachricht.
            4. $c$ ist der verschlüsselte Text. Die Abkürzung steht für _Cipher_.

14. Was ist ein XOR Cipher?

        Bei einem XOR Cipher wird die Klartextnachricht $m$ mithilfe eines Schlüssels $K$ mittels XOR-Operation verschlüsselt: $m \xor m = c$

15. Was bedeutet Interception?

    Interception passiert, wenn Nachrichten abgefangen werden. Das kann physisch, durch Veränderung der Verkabelung, oder logisch, durch Rekonfiguration von DNS oder ARP erfolgen.

16. Was bedeutet Eavesdropping?

    Eavesdropping ist das Abhören von Nachrichten. Das kann physisch, durch _Wiretapping_ oder Mitlesen des Netzwerkverkehrs, oder logisch durch die Umleitung des Verkehrs erfolgen.

17. Warum nennt man es einen passiven Angriff?

    Eavesdropping ist passiv, da der Angreifer den Datenverkehr nicht manipuliert.

18. Wie können Angreifer an die Daten herankommen?

        1. physisch: _Wiretapping_ oder Mitlesen des Netzwerkverkehrs.
        2. logisch: Umleitung des Verkehrs.

19. Wie kann Eavesdropping verhindert werden?

    Verschlüsselung der Nachrichten

20. Was versteht man unter lawful interception?

    "Lawful Interception (LI) ist ein Sicherheitsverfahren, bei dem ein Diensteanbieter oder Netzbetreiber die abgefangene Kommunikation von Privatpersonen oder Organisationen sammelt und den Strafverfolgungsbehörden zur Verfügung stellt."

21. Was ist eine Replay Attack?

    Eine Replay Attacke ist, wenn ein Angreifer eine Nachricht mitliest, kopiert und mehrmals an einen Empfänger sendet.

22. Wie können Replay Attacks verhindert werden?

    Mithilfe von Sequenznummern. Wenn dieselbe Nachricht mit derselben Sequenznummer gesendet wird, handelt es sich um dieselbe Nachricht und sollte trotz mehrfacher Wiederholungen als eine Nachricht behandelt werden.

23. Was ist eine Modification Attack?

    Eine Modification Attack ist eine aktive Attacke, bei der Angreifer Nachrichtenpakete bspw. modifiziert, umleitet und Schleifen erzeugt

24. Geben Sie Beispiele an!

    * Blackmail Attacke: einen scheinbar guten Knoten als schlecht markieren, indem er übersprungen wird

25. Erläutern Sie Gegenmaßnahmen!

    * Verschlüsselung: Indem der Nachrichteninhalt verschlüsselt wird, kann er nur vom vorgesehenen Empfänger entschlüsselt und gelesen werden. Durch die Verschlüsselung ist eine Modifikation ohne den Entschlüsselungsschlüssel nicht möglich und ein Angriff erschwert.
    * Signaturen: Durch Signaturen kann sichergestellt werden, dass die Nachricht vom vorgesehenen Sender gesendet wurde.

26. Was ist eine Impersonation Attack? Wie kann sie aussehen?

    Bei einer Impersonation Attacke gibt sich ein Angreifer als jemand anderes aus. Das kann in Form von IP- oder MAC-Adressen spoofing gelingen.

27. Was ist eine MitM attack?

    Ein besonderer Fall der Impersonation Attacke ist die Man-in-the-Middle Attacke, bei der sich ein Angreifer zwischen zwei kommunizierende Parteien einschleust, den Verkehr mitliest, manipuliert und versucht an sensible Informationen zu gelangen.

28. Wie kann sie verhindert werden?

    * Verschlüsselung: verschlüsselte Nachrichten können nur dem entsprechenden Schlüssel, den idealerweise nur der vorgesehene Empfänger besitzt, entschlüsselt werden.
    * Signaturen: Signaturen stellen sicher, dass Nachrichten nur vom erwarteten Sender gesendet wurden.

29. Was ist eine DoS attack?

    Denial-out-of-Service Attacken zielen darauf ein System durch eine Vielzahl von Anfragen zu beeinträchten bishin zum vollständigen Absturz.

30. Was bedeutet DDos?

    Distributed-DoS Attacken sind verteilte Attacken, bei denen meist ein Netzwerk aus mehreren tausend Rechnern versuchen ein System anzugreifen. Diese Rechner sind dann meist ungewollt Teil eines Bot-Netzes.

31. Geben Sie ein Beispiel für eine DoS attack an!

    SYN-Flooding: TCP Handshakes, bei denen der Angreifer die Antwortpakete nicht beantwortet, sodass der Server auf die Antwortpakete wartet und keine weiteren Verbindungen mehr aufbauen kann.

32. Was versteht man unter einer Amplified DDoS Attack?

    Amplified DDoS Attacken sind DDoS Attacken, bei denen der Angreifer die Antwortpakete so manipuliert, dass sie größer sind als die Anfragepakete. Dadurch wird der Server mit einer Vielzahl von großen Paketen überflutet. Die Leitung des Servers ist in diesen Fällen auch so überlastet, dass der Server nicht mehr nach Außen kommunizieren kann.

33. Beschreiben Sie wie eine NTP DDoS Attack funktioniert!

    NTP wird für die Zeitsynchronisierung verwendet. Das Verhältnis zwischen Anfragen:Antwort-Größe ist 1:20 bis 1:200. Schlecht konfigurierte NTP-Server können für Amplified DDoS Attacken verwendet werden, indem der Angreifer eine Anfrage mit einer gefälschten Absenderadresse an einen NTP-Server sendet. Der NTP-Server antwortet mit einer großen Antwort an die gefälschte Adresse.

34. Wie kann man dem on premise bzw. in der cloud begegnen?

    * On-premise: der Uplink muss größer sein, als die Angriffsbandbreite.
    * Cloud: der Provider muss die Angriffsbandbreite abwehren können.

35. Welche zwei Ansätze gibt es, um Verschlüsselung zu brechen?

36. Nennen sie zwei Arten von Angriffen, um Schlüssel herauszufinden!

37. Was versteht man unter Kryptoanalyse?

38. Welche drei unterschiedlichen Arten von Kryptoanalyse gibt es?

39. Was sind side channel attacks?

40. Wie funktioniert eine brute-force attack auf Passwörter bzw. auf Verschlüsselung?

41. Wovon hängen die Erfolgschancen von brute-force attacks vorwiegend ab?

42. Was ist eine dictionary attack?

43. Wie funktioniert statistische Kryptoanalyse mit cyphertext-only? Was ist eine Voraussetzung dafür?

44. Beschreiben Sie, wie eine Known-Plaintext Attack funktioniert?

45. Warum ist eine Chosen-Plaintext Attack wirkungsvoller?

46. Nennen Sie einen Satz mit 26 verschiedenen Buchstaben!

47. Was nutzen Side Channel Attacks aus? Nennen Sie Beispiele für Side Channel Attacks!

\section1.{Kapitel 2}

1. Nennen Sie eine allgemeine Notation für Verschlüsselung!

    $$c = E(K_e, m)$$

1. Was sind symmetrische und asymmetrische Kryptografie?

    Bei der 1.1.symmetrischen Kryptografie1.1. werden Texte mit einem symmetrischen Schlüssel verschlüsselt. Es kann sich dabei um den gleichen Schlüssel $K$ handeln, mit dem ein Text ver- und wieder entschlüsselt wird, oder, $K_d$ kann aus $K_e$ errechnet werden.
    Beispiele hierfür sind _One-time Pads}, \textit{Stream Cipher}, \textit{Block Cipher_.

    Bei der 1.1.asymmetrischen Kryptografie} gibt es zwei Schlüssel $K_e$ und $K_d$, wobei sich $K_d$ nicht aus $K_e$ errechnen lässt. Meistens ist $K_e$ öffentlich, während der $K_d$ privat bleiben muss, damit die Nachricht nicht von jedem entschlüsselt werden kann. Ein Beispiel hierfür ist \textbf{RSA1.1..

1. Was benötigt symmetrische Kryptografie, ehe sie angewendet werden kann?

    Für symmetrische Kryptografie muss der geteilte Schlüssel $K_s$ über einen sicheren Kanal ausgetauscht werden.

1. Was sind one-time pads?

    One-time Pads sind Schlüssel, die unter idealen Bedingungen _Perfect Privacy_  bieten und damit nicht knackbar sind. Mit ihnen werden Nachrichten mittels XOR-Operation verschlüsselt.
    Die Bedingungen für Perfect Privacy sind:

        1. zufälliger Schlüssel $K$
        1. $len(K) \geq len(m)$
        1. Schlüssel $K$ darf nur einmal genutzt werden

1. Was sind Stream Ciphers?

    Stream Cipher sind Key-Stream Generatoren, die einen Schlüssel $K$ bestimmter Länge um die Länger einer Nachricht $m$ expandieren. Mit diesem Key-Stream kann eine Nachricht bitweise mittels XOR Operation verschlüsselt werden.
    Stream Ciphers arbeiten mit Bits, während _Block Ciphers_ mit Blöcken arbeiten.

1. Was sind Block Ciphers?

    Mit Block Ciphers werden Nachrichten in einzelne, gleich große Blöcke unterteilt. Die Nachrichtenblöcke werden dann blockweise auf verschlüsselte Blöcke abgebildet.

1. Was ist ein Transposition Cipher?

    In einem Transposition Cipher werden nur die Positionen der einzelnen Buchstaben verändert.

1. Wie funktioniert ein Skytale? Was ist der Schlüssel?

    Ein Skytale ist ein Stab, der als Schlüssel fungiert, und um den ein Band, auf dem ein Text steht, gewickelt wird. Ohne den Stab sind die Buchstaben auf dem Band zusammengewürfelt. Erst durch das Wickeln um den Stab wird der Text erkenntlich gemacht.

1. Was ist ein Substitution Cipher? Was ist der Schüssel?

    Bei einem Substitution Cipher wird ein Buchstabe mit einem anderen substituiert. Der Schlüssel ist dabei die eindeutige Abbildung, von einem Buchstaben auf einen anderen. Das heißt, ein Buchstabe kann nicht auf zwei Buchstaben abgebildet werden, wodurch die eben die Eindeutigkeit nicht mehr gegeben wäre. Der Substitution Cipher ist ein _monoalphabetischer Cipher_.

1. Was ist Caesar’s Cipher? Was ist der Schlüssel?

    Der Caesar’s Cipher ist ein spezieller Fall eines monoalphabetischen Ciphers, bei dem alle Buchstaben in einem Text um einen bestimmten Schlüssel $K \in [0, 25]$ verschoben werden.
    Wenn der Schlüssel $K = 13$, spricht man auch von Caesar-ROT1.

    \enquote{Network Security ist spannend} wird bei $K = 13$ zu \enquote{arGJBEx frpHEvGL vFG FCnAArAq}, wobei dann N auf A, E auf R usw. abgebildet werden.

1. Was ist Polyalphabetic Substitution? Was ist der Schlüssel?

    Bei der polyalphabetischen Substitution werden mehrere Alphabete $n=3, M_1, M_3, M_7$ verwendet, um einen Text $m$ zu verschlüsseln. Dabei bestimmt die Position des zu substituierenden Buchstabens, welches Alphabet verwendet werden soll. Ein Doppelbuchstabe kann damit zu zwei verschiedenen Buchstaben substituiert werden, je nachdem, in welchem Alphabet sich dieser befindet. Da meist $len(m) \geq n$, rotieren die Alphabete in derselben Reihenfolge durch.

1. Nennen Sie einen bekannten Polyalphabetic Cipher!

    Ein bekanntes Beispiel ist der \href{<https://en.wikipedia.org/wiki/Vigenère_cipher}{Vigenère> cipher}.

1. Was ist der Unterschied zwischen einem RNG und einem echten PRNG?

    Der 1.1.R}andom \textbf{N}umber \textbf{G1.1.enerator (RNG) generiert echte Zufallszahlen auf der Basis von physikalischen Prozessen, wie Rauschen. Er ist nicht-deterministisch und unvorhersehbar.

    Der 1.1.P}seudo \textbf{R}andom \textbf{N}umber \textbf{G1.1.enerator (PRNG) generiert statistisch zufällige Zahlen auf Basis eines _Seeds_. Bleibt der Seed gleich, wird immer dieselbe Folge von Zufallszahlen generiert. Dieser Generator ist nicht kryptografisch sicher, da sich die Folge beobachten und vorhersagen lässt.

1. Was ist ein statistically secure PRNG?

    Ein statistisch sicherer PRNG unterscheidet sich vom PRNG insoweit, als, dass er zwar durch den Seed auch deterministisch, aber nicht vorhersehbar ist.

1. Wie funktioniert ein Stream Cipher? Beschreiben Sie seine Arbeitsweise mit geeigneter Notation! Was ist der Schlüssel?

    Ein Stream Cipher ist ein PRNG, bei dem der Seed als Schlüssel fungiert und bei dem eine Nachricht $m$ bitweise per XOR-Operation mit dem Keystream $ks$ verschlüsselt wird.

        1. Verschlüsselung: $c(i) = ks(i) \xor m(i)$.
        1. Entschlüsselung: $m(i) = ks(i) \xor c(i)$

    Der Schlüssel ist symmetrisch.

1. Nennen Sie Vorteile von Stream Ciphers!

        1. Verschlüsselung von einem Bit auf einmal. Das heißt, der Sender kann direkt verschlüsseln, ohne auf ganze Blöcke zu warten, wie es beim Block Cipher der Fall ist. Stream Cipher eignen sich damit für Realzeitanwendungen.
        1. Singlebit-Fehler im Ciphertext $c$ führen zu Singlebit-Fehlern im Klartext $m$ und können mithilfe der _Forward Error Correction (FEC)_ korrigiert werden.

1. Wofür steht RC4?

    \enquote{Ron's Cipher 4} ist ein (Byte-orientierter) Stream Cipher.

1. Was ist ein Vorteil von RC4?

        1. variable Schlüssellänge,
        1. performant,
        1. einfacher Algorithmus, der sich damit auch einfach implementieren lässt. Das führt wiederum zur Minimierung von Fehlern bei der Implementierung und der Verminderung von _Side-Channel Attacken_.

1. Was ist _Key Scheduling_ in RC4? Wie funktioniert es in Grundzügen?

    Key Scheduling dient dazu eine Substitutionstabelle

1. Wie funktioniert die RC4 Verschlüsselung in Grundzügen? Wie viele zufällige Bits werden dabei auf einmal erzeugt? Auf welcher internen Datenstruktur arbeitet RC4? Wie wird diese im Laufe
der Verschlüsselung verändert?

    RC4 besteht aus zwei Schritten:

        1. Key Scheduling: Zustand initialisieren
        1. Verschlüsselung: Keystream generieren und den Klartext-Stream mit dem Keystream per XOR-Operation verschlüsseln

    Es werden $m$-viele Bits erzeugt, wobei $m$ die Länge der Nachricht, die verschlüsselt werden soll, ist. RC4 baut auf einer Substitutions-Box, kurz _S-Box_. Diese Struktur wird so verändert, dass Buchstaben mit den Indexen $i = (i + 1) (mod 256)$ und $j = (j + S[i]) (mod 256)$ miteinander vertauscht werden.

1. Erläutern Sie T[] und S[], wofür sie verwendet werden, und wie der Schlüssel verwendet wird!

    $S$[] ist die S-Box mit einer Länge von 255 Bytes. $T$[] ist ein temporäres Array, das verwendet wird, um die S-Box zu befüllen. Am Anfang ist die S-Box nur mit den Werten von 0 bis 255 befüllt. In $T$ wird der Schlüssel $K$ mehrere Male hintereinander gereiht, da der Schlüssel $K$ kleiner als die maximale Länge von $255 B = 2048 Bits$ sein kann. Die S-Box wird dann mithilfe von T, das potenziell mehrere Kopien des Schlüssels enthält, permutiert.

1. Wofür wird RC4 verwendet?

        1. WiFi: WEP, WPA, WPA2
        1. Microsoft Point-to-Point Encryption Protocol
        1. Remote Desktop Protocol

1. Ist die Verwendung von RC4 empfehlenswert?

    Nein, da RC4 heutzutage als unsicher betrachtet wird. Anfangs wurde RC4 geheim gehalten, um Sicherheit durch die Geheimhaltung des Algorithmus zu garantieren.

1. Wie funktioniert Salsa20 in Grundzügen? Wie viele zufällige Bits werden dabei auf einmal erzeugt?
Auf welcher internen Datenstruktur arbeitet Salsa20? Wie wird diese im Laufe der
Verschlüsselung verändert?

1. Was ist ChaCha? Wie unterscheidet es sich von Salsa20? Was ist der Vorteil?

1. Wo wird ChaCha verwendet?

1. Welche Stream Ciphers kennen Sie noch? Welche davon sind noch empfehlenswert?

1. Wie funktioniert ein Block Cipher prinzipiell?

1. Was ist das Problem bei einer naiven Implementierung und wie wird das Problem ge-
löst?

1. Was ist ein Feistel Cipher? Wie funktioniert er? Welche Methoden basieren auf Feistel
Ciphers?

1. Was heißt DES? Was heißt NIST? Was heißt FIPS?

1. Wie groß ist die Block Size bei DES, wie groß der Schlüssel? Was sind round keys?

1. Warum benötigt DES einen Key Schedule? Was macht er?

1. Was ist eine S-box? Was ist eine P-box?

1. Wie funktioniert die Entschlüsselung mit DES?

1. Was sind Schwächen von DES?

1. Was ist Triple-DES (3DES)? Was ist seine key size?

1. Warum wird nicht 2DES verwendet?

1. Wird 3DES verwendet? Welches Problem von DES wird durch 3DES nicht gelöst?

1. Was ist ein weiterer Nachteil von 3DES gegenüber neueren Ciphers?
1. Was bedeutet AES? Welche Block Size hat er? Welche Key Sizes unterstützt er?

1. Wie steht es mit der Performance von AES?

1. Wie funktioniert AES strukturell?

1. Wie geht der Schlüssel ein?

1. Warum benötigt man einen Key Scheduling Algorithm?

1. Warum werden Operation Modes für Block Ciphers verwendet?

1. Was heißt ECB und wie funktioniert es? Was sind seine Probleme?

1. Was heißt CBC und wie funktioniert es? Was sind seine Probleme?

1. Was heißt CTR und wie funktioniert es? Was sind seine Probleme?

1. Was bedeutet synchronous im Kontext von ciphers? Geben Sie zwei Beispiele an!

1. Was sind self-synchronization block ciphers?

1. Was heißt OFB und wie funktioniert es? Was sind seine Probleme?

1. Was heißt CFB und wie funktioniert es? Was sind seine Probleme?

1. Was ist eine Hash Funktion?

1. Geben Sie einfache Hashes an und diskutieren Sie deren Probleme im Kontext Krypto-
graphie!

1. Was ist für kryptografische Hashes essenziell?

1. Welche Arten von _Resistance_ kennen sie und was bedeuten sie?

1. Nennen Sie Synonyme für kryptografische Hashes!

1. Warum ist die Internet Checksumme kein guter Message Digest?

1. Was ist Ziel und Funktionsweise der Merkle-Damgard-Construction?

1. Warum benötigt man dafür einen IV? Warum benötigt man padding?

1. Was heißt MD5? Nach welchem Prinzip funktioniert MD5? Was ist seine Blockgröße? Wie groß ist seine Digest Sizes?

1. Ist MD5 noch sicher? Wofür kann er verwendet werden?

1. Was heißt SHA?

    SHA steht für 1.1.S}ecure \textbf{H}ash \textbf{A1.1.lgorithm.

1. Nach welchem Prinzip funktioniert SHA-1? Was ist seine Blockgröße? Was ist seine
Digest Size? Welche Attacke gibt es gegen SHA-1?

    SHA-1 ist eine Merkle-Damgard Konstruktion. Es gibt eine Blockgröße von 512 Bit und hat einen _Message Digest_ von 160 Bit. Der Message Digest ist ein Hash-Output.

    Gegen SHA-1 gibt es die 1.1.Collision-Attack1.1.. Das bedeutet, dass zwei verschiedene Inputs zum selben Output führen.

1. Was ist ein wesentlicher Unterschied zwischen SHA-1 und SHA-2? Welche Varianten gibt
es?

    SHA-2 produziert im Vergleich zu SHA-1 längere Digests.

1. Was ist SHA-3?

1. Was sind Message Authentication Codes? Was sind Synonyme?

1. Was ist das Problem bei Simpled Keyed Hashes?

1. Was ist HMAC und wie funktioniert es?

    HMAC steht für Keyed-1.1.H}ashing \textbf{M}essage \textbf{A}thentication \textbf{C1.1.ode und ist eine standardisierte Einweg-Hashfunktionen, die mit einem Schlüssel $k$ arbeitet, aber Hashes anstelle von Verschlüsselung verwendet.

    $t = H(k \xor opad |H(k \xor ipad|m))$

1. Was können Sie über seine Sicherheit aussagen?

1. Was ist CBC-MAC? Was ist ein Problem und eine Gegenmaßnahme?

1. Was ist Poly1305? Wie funktioniert es strukturell? Woher kommt sein Name?

1. Was bedeutet (Non-)Malleability? Geben Sie Beispiele an!

1. Was ist authenticated encryption? Was sind Ziele?

1. Was heißt AEAD und was ist damit gemeint? Wie funktioniert AEAD?

1. Was bedeuten MAC-and-encrypt, MAC-then-encrypt, Encrypt-then-MAC?

1. Diskutieren Sie die Sicherheit dieser Varianten!

1. Was heißt CCM? Was sind Vorteile? Wie funktioniert es? Wie funktioniert die AEAD
version? Wo wird CCM angewendet?

1. Was heißt GCM? Wie funktioniert es? Was sind seine Vorteile?

1. Was ist GMAC?

1. Was ist ChaCha20-Poly1305? Wie funktioniert es strukturell?

1. Was ist ein grundlegender Unterschied zwischen symmetrischer und asymmetrischer
Kryptografie?

1. Wie funktioniert Public Key Kryptografie?

1. Warum kann bei symmetrischer Kryptografie der Key, der zur Verschlüsselung genutzt wird, nicht veröffentlicht werden?

1. Was ist der kleinste gemeinsame Teiler von 169 und 221?

1. Was ist $\phi(50)$?

1. Was ist $\phi(5917)$? Hinweis: Die Primfaktoren von 5917 lauten 61 und     1.

1. Auf welchen Problemen der Zahlentheorie basiert die meiste asymmetrische Kryptografie?

1. Warum ist es im Kontext von RSA wichtig, dass d und e inverse zueinander sind?

1. Warum ist es schwer $\phi(n)$ zu berechnen, wenn nur n und e bekannt sind?

1. Was passiert beim vorgestellten Textbook RSA, wenn zweimal dieselbe Nachricht
verschlüsselt wird? Wie kann dieses Problem behoben werden?

1. Wie viele Multiplikationen sind notwendig, um 139118 zu berechnen, wenn der naive
Algorithmus aus der Schule verwendet wird?

1. Wie viele Multiplikationen sind notwendig mit dem Square-and-Multiply Algorithmus?

1. Leiten Sie aus den Eigenschaften einer Gruppe her, dass das neutrale Element in einer
Gruppe eindeutig ist!

1. Was ist ein Shared Secret? Wie bekommen beide Kommunikationspartner das shared secret?

1. Was ist non-repudiation?

1. Vergleiche RSA Signaturen mit dem normalen RSA Algorithmus!

1. Warum darf $k$ im Kontext von DSA nie mehrfach verwendet werden?

1. Wie funktioniert ElGamal?

    ElGamal wird mithilfe eines Beispiels erklärt, bei dem Alice eine Nachricht verschlüsselt an Bob senden möchte.

    Bei 1.1.ElGamal} wählt Alice ein zufälliges $y \in \{1, 2, ..., q - 1\}$, das nur einmal verwendet werden sollte, und berechnet mit $y$ und mit Bobs öffentlichem Schlüssel $h_{Bob}$ ein Shared Secret $s = h_{Bob}^y = (g^{x_{Bob}})^{y} = g^{xy}$. $h_{Bob} = g^{x_{Bob}}$ ist Bobs öffentlicher Schlüssel und $x_{Bob1.1.$ ist Bobs privater Schlüssel. Bei $g$ handelt es sich um einen Generator der Gruppe $G$.
    Mit $s$ kann Alice die Nachricht $m$ verschlüsseln, sodass sie $c_2 = m 1. s$ erhält. Zusätzlich zur Nachricht gibt sie $c_1 = g^{y}$ mit.
    Bob kann $m$ aus $m = (c_1)^{-x} 1. c_2 = ((g^{y})^{-x}) 1. (g^{xy} 1. m) = g^{-xy+xy} 1. m = g^{0} 1. m$ berechnen. Bob kennt $x$, da es sich um seinen privaten Schlüssel handelt.

    Beide Parteien können das Shared Secret $s$ ausrechnen. Alice rechnet $s = (g^{x_{Bob}})^{y} = g^{xy}$ aus und Bob rechnet $s = (g^{y})^{x_{Bob}} = g^{xy}$ aus.

1. Wozu wird der Diffie-Hellman Schlüsseltausch verwendet?

1. Was hat Diffie-Hellman mit ElGamal zu tun?

    Diffie-Hellmann und ElGamal beruhen beide auf dem Prinzip des _Shared Secrets_, das sich beide Parteien jeweils berechnen, und auf Operationen, die in einer Gruppe $G$ ausgeführt werden.

1. Was weiß ein Angreifer, der die gesamte Kommunikation eines Diffie-Hellmann Schlüsselaustausch mitgehört hat? Kann er damit das Shared Secret berechnen?

1. Definieren Sie Forward-secrecy! (Notwendig!)

    Forward secrecy

1. Angenommen ein Angreifer hört die Kommunikation eines DH Schlüsseltauschs ab. Zu
einem späteren Zeitpunkt nach dem Austausch findet der Angreifer die Private Keys für die
verwendeten Signaturen heraus. Warum nützt ihm dies nichts?

1. Machen Sie sich über die Folien hinaus mit elliptischen Kurven über R vertraut:
<https://andrea.corbellini.name/ecc/interactive/reals-add.html>.

1. Machen Sie sich auch mit elliptischen Kurven über einem endlichen Körper \href{<https://andrea.corbellini.name/ecc/interactive/modk-add.html}{vertraut}>:

1. Wie lautet die \enquote{Regel}, mit der aus klassischen Verfahren ein Verfahren mit
elliptischen Kurven konstruiert werden kann?

1. Was sind die Vorteile von elliptischen Kurven gegenüber klassischer asymmetrischer Kryptografie?

1. Welche Vorteile bietet Curve25519?

Zusatz: Informieren Sie sich über \href{<https://en.wikipedia.org/wiki/Dual_EC_DRBG}{Wikipedia}> über ein Verfahren mit elliptischen Kurven, dass diese Vorteile nicht bietet!

1. Welche Vorteile bieten symmetrische und asymmetrische Kryptografie?

1. Wie können die Vorteile von symmetrischer und asymmetrischer Kryptografie kombiniert
werden?

1. Vergleichen Sie die Sicherheit von RSA und ECC bei einer festen vorgegebenen Schlüssellänge!

1. Was können Quantencomputer effizient tun, was klassische Computer nicht können?

1. Ist symmetrische Kryptografie anfällig für Angriffe durch Quantencomputer?

\end{document}