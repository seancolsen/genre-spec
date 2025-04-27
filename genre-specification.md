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

- `.rfor` - standard 4:4 beat
- `.rtwo` - down beat, house, dance
- `.rsix` - 3:4 or 6:8, waltz
- `.rodd` - odd time signature
- `.rodd##` - an odd time signature with `##` beats where `##` is a zero-padded number 
- `.rmul` - multiple rhythmic feelings overlaid simultaneously. Common in 6:8 Ethiopian jazz.
- `.rspt` - split -- different time signatures, one measure after the other
- `.rspt##&&` - a split time signature with `##` beats and then `&&` beats
- `.rl*s*` - a rhythm with a mix of "long" beats (three) and "short" beats (two). Any number of `l` and `s` entries may be present here. For example `.rlss`, `.rsls`, and `.rssl` would all have a 7:8 time signature but would each have their own feel. Some esoteric jazz songs can get even crazier like "Samai Thaquil" by "Karl Hector & the Malcouns" which is `.rllllssss`.
- `.rdnb` - drums and bass beat (fast)
- `.rfnk` - funk
- `.ronk` - rock funk
- `.rreg` - reggae, slow "and" beats
- `.rdub` - dub
- `.rdhl` - dancehall 
- `.rska` - ska, faster "and" beats
- `.rpkr` - punk rock (fast 4:4)
- `.rpkf` - punk (fast cut time)
- `.rmos` - mosh / break down / chug
- `.rgnd` - grind (double cut time)
- `.rmet` - metal / double bass pedal fast 4:4 with lots of cymbals
- `.rglc` - glitch
- `.roff` - even time signature emphasizing off beats in an unusual way
- `.rlat` - latin
- `.ramb` - ambient, minimal or no rhythm
- `.rplk` - polka, down-up, down-up
- `.rdsc` - disco
- `.rrnr` - rock 'n roll (1950's 1960's style) fast, finger snapping
- `.rohh` - old skool hip hop
- `.rbnc` - bounce
- `.rpha` - phasing (e.g Steve Reich)

### Notes

- `.nctr` - country
- `.npop` - pop / melodic
- `.nclt` - celtic
- `.ndst` - guitar with heavy distortion
- `.ncmt` - classic metal, guitar solos, some distortion
- `.nblk` - balkan
- `.nfcr` - fast circus music
- `.ncir` - circus
- `.narb` - middle eastern 
- `.nbly` - bellydance
- `.neth` - ethiopian
- `.nafr` - african
- `.nnai` - native american / american indian
- `.ncls` - classical
- `.nsco` - film score sounding
- `.nreg` - reggae
- `.ndub` - dub
- `.ndbs` - dubstep
- `.nska` - ska
- `.nlat` - latin
- `.namb` - ambient, minimal or no melody
- `.nswg` - swing
- `.ngjz` - gypsy jazz
- `.nage` - new age
- `.nmic` - microtonal
- `.nohh` - old skool hip hop
- `.njaz` - jazz
- `.njam` - jam band
- `.ngru` - grunge
- `.nflm` - flamenco
- `.nrnb` - R & B
- `.nsft` - soft rock
- `.ndro` - drone
- `.nbas` - nice bass
- `.nhos` - house
- `.nblu` - blues
- `.nzyd` - zydeco
- `.nbhg` - indian / bhangra / punjabi
- `.nflk` - folk
- `.nfnk` - funk
- `.nslo` - chopped and screwed / slowed-down
- `.nafb` - afrobeat
- `.nbal` - balearic 
- `.nais` - asian
- `.nsol` - soul
- `.natl` - atonal 
- `.nois` - noise
- `.npsy` - psychedelic
- `.nsmb` - samba
- `.nwes` - western / cowboy / spaghetti western
- `.n8bt` - 8 bit
- `.ncmb` - cumbia 
- `.ntrp` - trap
- `.nmoo` - moombahton
- `.ncar` - Caribbean / Soca / calypso
- `.nhlf` - high life
- `.notm` - old time

### Scale

- `.smaj`    - major
- `.sminnat` - natural minor
- `.sminhar` - harmonic minor
- `.sminmel` - melodic minor
- `.sdblhar` - double harmonic
- `.shungyp` - hungarian gypsy
- `.sphrygd` - phrygian dominant
- `.sphrygn` - phrygian
- `.sunk`    - unknown
- `.s####`   - a numerical representation of the scale as the decimal equivalent of a big-endian binary number with every active interval set to 1. For example, a major scale would be `0b101010110101` which equals `2741`, so we would write `.s2741`. Similarly, the major pentatonic scale is `0b001010010101` which equals `661` so we would write `.s0661`. Note that the decimal number should be zero padded to 4 decimal places when written into the genre string. See [Octave Compass](https://octavecompass.com/2741) for an interactive tool. 

### Key

- `.kfn` - F natural
- `.kcn` - C natural
- `.kgn` - G natural
- `.kdn` - D natural
- `.kan` - A natural
- `.ken` - E natural
- `.kbn` - B natural
- `.kgf` - G flat
- `.kdf` - D flat
- `.kaf` - A flat
- `.kef` - E flat
- `.kbf` - B flat
- `.k##` - a numerical representation of the key with C being 00 and B being 11

### Vocal-type

- `.vcs`  - casual singing
- `.vss`  - serious singing
- `.vch`  - choir
- `.vsp`  - samples
- `.vtk`  - half way between singing and talking
- `.vag`  - aggressive singing, more mainstream than punk
- `.vpk`  - punk, agressive singing
- `.vhh`  - hip hop
- `.vxx`  - screamo / grind / hardcore metal that is not easily understandable
- `.vhc`  - hardcore punk talking/singing that is mostly understandable
- `.vrc`  - rap core / rap metal
- `.vms`  - pop / club / urban / mainstream
- `.vdw`  - doo wop / multi-part harmonies / oldies
- `.vhr`  - strong vocal harmonies
- `.vsh`  - shanty
- `.vsc`  - scat
- `.vjm`  - jamaican
- `.vyd`  - yodeling
- `.vsy`  - sythesized
- `.vat`  - auto-tune
- `.vps`  - pitch-shifted 
- `.vug`  - ugly (eg. Tom Waits)
- `.voc`  - vocoder
- `.vrnb` - R & B
- `.vcmt` - classic metal / high-pitch harmonies / hair metal
- `.vbhg` - indian singing / bhangra / punjabi
- `.vcht` - chanting
- `.vblk` - balkan / eastern european
- `.vswg` - swing
- `.vfnk` - funk
- `.vgru` - grunge
- `.vohh` - old skool hip hop
- `.vgsp` - gospel

### Language

- `.lne` - not english

### Attitude

- `.ao` - offensive
- `.au` - uncomfortable
- `.ai` - politically incorrect
- `.aa` - annoying
- `.al` - liberal
- `.ax` - sexual
- `.aq` - queer
- `.ar` - radical
- `.ag` - goofy
- `.at` - religious
- `.aj` - marijuana
- `.am` - misogynist 
- `.av` - violent

### Feeling

- `.fsad` - sad
- `.fhap` - happy
- `.fnos` - nostalgic
- `.fboo` - scary
- `.fdrk` - dark
- `.fawe` - song itself is awe inspiring -- chord progression, composition, lyrics, etc. completely distract me from whatever else I'm doing at the moment, so that all I can do is listen to the song, in awe.

### Instruments

- `.iacd` - accordion / concertina
- `.ibag` - bagpipe
- `.ibbx` - beat box
- `.ibel` - bells / toy piano / chimes
- `.ibjo` - banjo
- `.ibrs` - brass
- `.icrd` - crowd noise (as in a live performance)
- `.icrp` - drum corps
- `.icim` - hammered dulcimer / cimbalom / santur
- `.idjg` - didgerido
- `.idst` - distorted guitar
- `.ihar` - harmonica
- `.ihur` - hurdy gurdy
- `.ihdm` - hand drums
- `.ihrp` - harp
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
- `.iwnd` - wind: flute, recorder
- `.iwsl` - whistle
- `.ivib` - vibriphone
- `.izur` - zurna

### Extra

- `.xcov` - cover of another artist's song (but sounding pretty similar)
- `.xrmx` - remix of an easily identifiable song, but with a new sound
- `.xmsh` - mashup of other songs
- `.xprd` - parody of another song
