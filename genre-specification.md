# Sean Colsen's music genre name specification

Purpose:

- Given a large number of musical pieces (songs), we would like to develop a system of categorizing them such that we can efficiently and straightforwardly retrieve a set of songs that is suitable to a given mood and contains a diverse mix of artists.
- This document specifies a format for generating one string that encapsulates a subjective representation of the "genre" for each song. This string is called the "genre string"
- With all songs having a genre string, we can easily query the set of genre strings to match a variety of constraints. 

How to:

- Listed below are many genre elements which represent various measurements that can be taken (qualitatively) from each song.
- Each element has many values which are listed below the element name.
- Each value has an abbreviation (listed first) and then a description (listed after one space, one dash, and one space).
- The complete genre string for each song is formed by concatenating all of the applicable genre values in the order they are listed on this page.
- Also, as a reference, there are hyper-values listed at the end of this specification that match genre values in multiple elements. Hyper-values are not written into the genre string.

Example:

- The following genre string of would represent a chill song with decent rhythm, some electronic elements, very underground, singing vocals throughout the song that aren't in english, some rhythm constructions from dub music, some melody constructions from balkan music, and brass instruments.

    ```
    e2.d3.t3.m1.p3.rdub.nblk.vcs.lne.ibrs
    ```

## Required elements

_(Only one value is permitted per-group, and they should always appear in the order listed below.)_

### Energy

- `e1` - really chill, sleepy, relaxed
- `e2` - chill, hang out, relaxed
- `e3` - some energy, but not a whole lot
- `e4` - lots of energy
- `e5` - really crazy

### Dance

- `.d1` - not very much rhythm
- `.d2` - normal amount of rhythm, foot tapping and finger tapping
- `.d3` - very strong rhythm, head bobbing and shoulder moving difficult to avoid
- `.d4` - worthy of full-body dancing
- `.d5` - crazy hard dancing difficult to avoid

### Technology

- `.t1` - everything acoustic
- `.t2` - some amplified sound like electric guitar
- `.t3` - a mix of acoustic stuff and electronic stuff
- `.t4` - mostly electronic stuff
- `.t5` - everything electronic

### Mainstream

- `.m1` - very underground sounding
- `.m2` - indie sounding
- `.m3` - kind of indie, wouldn't be out of place on the radio though
- `.m4` - pretty mainstream sounding, but maybe not everyone has heard it
- `.m5` - top 40s

### Presence-of-vocals

- `.p0` - none
- `.p1` - abstract or minimalistic
- `.p2` - somewhat present vocals
- `.p3` - present vocals
- `.p4` - vocals are the main focus of the track

## Optional elements

_(Multiple values are possible. The groups should appear in the order below. But within each group the most relevant items should be listed first.)

### Rhythm-type

- `.ramb` - ambient, minimal or no rhythm
- `.rbnc` - bounce
- `.rdhl` - dancehall 
- `.rdnb` - drums and bass beat (fast)
- `.rdsc` - disco
- `.rdub` - dub
- `.rfnk` - funk
- `.rfor` - standard 4:4 beat
- `.rglc` - glitch
- `.rgnd` - grind (double cut time)
- `.rl*s*` - a rhythm with a mix of "long" beats (three) and "short" beats (two). Any number of `l` and `s` entries may be present here. For example `.rlss`, `.rsls`, and `.rssl` would all have a 7:8 time signature but would each have their own feel. Some esoteric jazz songs can get even crazier like "Samai Thaquil" by "Karl Hector & the Malcouns" which is `.rllllssss`.
- `.rlat` - latin
- `.rmet` - metal / double bass pedal fast 4:4 with lots of cymbals
- `.rmos` - mosh / break down / chug
- `.rmul` - multiple rhythmic feelings overlaid simultaneously. Common in 6:8 Ethiopian jazz.
- `.rodd##` - an odd time signature with `##` beats where `##` is a zero-padded number 
- `.rodd` - odd time signature
- `.roff` - even time signature emphasizing off beats in an unusual way
- `.rohh` - old skool hip hop
- `.ronk` - rock funk
- `.rpha` - phasing (e.g Steve Reich)
- `.rpkf` - punk (fast cut time)
- `.rpkr` - punk rock (fast 4:4)
- `.rplk` - polka, down-up, down-up
- `.rreg` - reggae, slow "and" beats
- `.rrnr` - rock 'n roll (1950's 1960's style) fast, finger snapping
- `.rsix` - 3:4 or 6:8, waltz
- `.rska` - ska, faster "and" beats
- `.rspt##&&` - a split time signature with `##` beats and then `&&` beats
- `.rspt` - split -- different time signatures, one measure after the other
- `.rtwo` - down beat, house, dance

### Notes

- `.n8bt` - 8 bit
- `.nafb` - afrobeat
- `.nafr` - african
- `.nage` - new age
- `.nais` - asian
- `.namb` - ambient, minimal or no melody
- `.narb` - middle eastern 
- `.natl` - atonal 
- `.nbal` - balearic 
- `.nbas` - nice bass
- `.nbhg` - indian / bhangra / punjabi
- `.nblk` - balkan
- `.nblu` - blues
- `.nbly` - bellydance
- `.ncar` - Caribbean / Soca / calypso
- `.ncir` - circus
- `.ncls` - classical
- `.nclt` - celtic
- `.ncmb` - cumbia 
- `.ncmt` - classic metal, guitar solos, some distortion
- `.nctr` - country
- `.ndbs` - dubstep
- `.ndro` - drone
- `.ndst` - guitar with heavy distortion
- `.ndub` - dub
- `.neth` - ethiopian
- `.nfcr` - fast circus music
- `.nflk` - folk
- `.nflm` - flamenco
- `.nfnk` - funk
- `.ngjz` - gypsy jazz
- `.ngru` - grunge
- `.nhlf` - high life
- `.nhos` - house
- `.njam` - jam band
- `.njaz` - jazz
- `.nlat` - latin
- `.nmic` - microtonal
- `.nmoo` - moombahton
- `.nnai` - native american / american indian
- `.nohh` - old skool hip hop
- `.nois` - noise
- `.notm` - old time
- `.npop` - pop / melodic
- `.npsy` - psychedelic
- `.nreg` - reggae
- `.nrnb` - R & B
- `.nsco` - film score sounding
- `.nsft` - soft rock
- `.nska` - ska
- `.nslo` - chopped and screwed / slowed-down
- `.nsmb` - samba
- `.nsol` - soul
- `.nswg` - swing
- `.ntrp` - trap
- `.nwes` - western / cowboy / spaghetti western
- `.nzyd` - zydeco

### Scale

- `.s####`   - a numerical representation of the scale as the decimal equivalent of a big-endian binary number with every active interval set to 1. For example, a major scale would be `0b101010110101` which equals `2741`, so we would write `.s2741`. Similarly, the major pentatonic scale is `0b001010010101` which equals `661` so we would write `.s0661`. Note that the decimal number should be zero padded to 4 decimal places when written into the genre string. See [Octave Compass](https://octavecompass.com/2741) for an interactive tool. 
- `.sdblhar` - double harmonic
- `.shungyp` - hungarian gypsy
- `.smaj`    - major
- `.sminhar` - harmonic minor
- `.sminmel` - melodic minor
- `.sminnat` - natural minor
- `.sphrygd` - phrygian dominant
- `.sphrygn` - phrygian
- `.sunk`    - unknown

### Key

- `.k##` - a numerical representation of the key with C being 00 and B being 11
- `.kaf` - A flat
- `.kan` - A natural
- `.kbf` - B flat
- `.kbn` - B natural
- `.kcn` - C natural
- `.kdf` - D flat
- `.kdn` - D natural
- `.kef` - E flat
- `.ken` - E natural
- `.kfn` - F natural
- `.kgf` - G flat
- `.kgn` - G natural

### Vocal-type

- `.vag`  - aggressive singing, more mainstream than punk
- `.vat`  - auto-tune
- `.vbhg` - indian singing / bhangra / punjabi
- `.vblk` - balkan / eastern european
- `.vch`  - choir
- `.vcht` - chanting
- `.vcmt` - classic metal / high-pitch harmonies / hair metal
- `.vcs`  - casual singing
- `.vdw`  - doo wop / multi-part harmonies / oldies
- `.vfnk` - funk
- `.vgru` - grunge
- `.vgsp` - gospel
- `.vhc`  - hardcore punk talking/singing that is mostly understandable
- `.vhh`  - hip hop
- `.vhr`  - strong vocal harmonies
- `.vjm`  - jamaican
- `.vms`  - pop / club / urban / mainstream
- `.voc`  - vocoder
- `.vohh` - old skool hip hop
- `.vpk`  - punk, agressive singing
- `.vps`  - pitch-shifted 
- `.vrc`  - rap core / rap metal
- `.vrnb` - R & B
- `.vsc`  - scat
- `.vsh`  - shanty
- `.vsp`  - samples
- `.vss`  - serious singing
- `.vswg` - swing
- `.vsy`  - sythesized
- `.vtk`  - half way between singing and talking
- `.vug`  - ugly (eg. Tom Waits)
- `.vxx`  - screamo / grind / hardcore metal that is not easily understandable
- `.vyd`  - yodeling

### Language

- `.lne` - not english

### Attitude

- `.aa` - annoying
- `.ach` - Christmas
- `.ag` - goofy
- `.ai` - politically incorrect
- `.aj` - marijuana
- `.al` - liberal
- `.am` - misogynist 
- `.ao` - offensive
- `.aq` - queer
- `.ar` - radical
- `.at` - religious
- `.au` - uncomfortable
- `.av` - violent
- `.ax` - sexual

### Feeling

- `.fawe` - song itself is awe inspiring -- chord progression, composition, lyrics, etc. completely distract me from whatever else I'm doing at the moment, so that all I can do is listen to the song, in awe.
- `.fboo` - scary
- `.fdrk` - dark
- `.fhap` - happy
- `.fnos` - nostalgic
- `.fsad` - sad

### Instruments

- `.iacd` - accordion / concertina
- `.ibag` - bagpipe
- `.ibbx` - beat box
- `.ibel` - bells / toy piano / chimes
- `.ibjo` - banjo
- `.ibrs` - brass
- `.icim` - hammered dulcimer / cimbalom / santur
- `.icrd` - crowd noise (as in a live performance)
- `.icrp` - drum corps
- `.idjg` - didgerido
- `.idst` - distorted guitar
- `.ihar` - harmonica
- `.ihdm` - hand drums
- `.ihrp` - harp
- `.ihur` - hurdy gurdy
- `.imal` - mallet
- `.imel` - melodica
- `.imnd` - mandolin
- `.iorg` - organ
- `.ipia` - piano
- `.ired` - reed driven brass/wood: clarinet, saxaphone
- `.isaw` - saw
- `.ishp` - shephard tone
- `.isit` - sitar
- `.islg` - slide guitar
- `.istd` - steel drum
- `.istr` - strings
- `.itap` - tap dancing
- `.itbl` - turn table scratching 
- `.iuke` - ukulele
- `.ivib` - vibriphone
- `.iwnd` - wind: flute, recorder
- `.iwsl` - whistle
- `.izur` - zurna

### Extra

- `.xcov` - cover of another artist's song (but sounding pretty similar)
- `.xmsh` - mashup of other songs
- `.xprd` - parody of another song
- `.xrmx` - remix of an easily identifiable song, but with a new sound
