
 
So, I just recently made the switch to a mac mini. I have most of my music stored on a pc on my network. This is all stored in flac, I want to use itunes as my primary music player, and dont want to use a program like fluke every time I want to import music.
 
So I think that I would rather have everything stored in AIFF. (Is this better to use than wav?) My question is if I convert my flac collection to AIFF, will I gain, lose or just keep the exact same quality as the flac files I converted from???
 
**Download Zip » [https://amreamate.blogspot.com/?d=2A0SNP](https://amreamate.blogspot.com/?d=2A0SNP)**


 
I guess this really didnt cover what I was asking. And since FLAC is a compressed lossless format, I am looking for uncompressed lossless which is why I am inquiring about AIFF. Also I am wanting to use itunes which FLAC is not natively supported by.
 
You can rest assured that if you convert all your FLAC files to AIFF you will **not** gain, will **not** lose but will keep, **exactly** the same quality. However, you will of course lose some disk space.
 
I'm channeling Ashley/Tim/et al here, but you should probably compare any program you are considering against iTunes to see if you can hear the difference before selecting something other than iTunes.
 
I am going to second David and say go with AIFF. Storage space is cheap these days and you never have to worry if you are missing something. I use AIFF when I convert the FLAC files I download from Archive.org and the results are stunning.
 
Not sure about the 'best way', but I use TuneUp to find metadata/artwork for audio files that were NOT ripped by iTunes. [note: Get Album Artwork function in iTUnes only works when iTunes is used to 'rip' the files]
 
Ok, so i am feeling strong about my original thought about converting everything to AIFF via max. I have done a few test runs, importing straight to itunes and preserving all of the tags. Only problem is there anyway to batch convert an entire directory?? With a several hundred flac albums one at a time is a daunting task. I guess I could use dbpoweramp to batch convert everything, but would like to do everything by mac if possible.

I can also highly recommend XLD for conversions. It will show an error if the source file is not perfect (skips, etc). It supports full tag transfer into/from AIFF and can also split single flac/cue into multiple files.
 
I'm sort of new to this but have been involved in the live engineering side of the music business for years. Stumbling upon Fluke for Flac conversion raises some questions for me. Why does it want to convert to a quicktime file? even though it does put the files in itunes why don't i have a choice as to the converted format? Does it really matter? For some reason it won't play the music files over my wifi networked audio system but will play on the computer itself. Baffling me. Very cool stuff this is.
 
I've found max which seems to be what I was looking for in the first place. Appears to interface with itunes. Learning curve is happening here. thanks for the reply. I'm open to any direction you can lead me.
 
Have a look at MP3TAG. Has a lot of information that you can view and sort by. And it does work on other file types. Automating something like this could be dangerous. Yes it will take some time but at least you will know what it is doing. And you can update tags and artwork at the same time if they are missing.
 
I will delve into the the details of these 3 programs to determine which appears to be best. If trials are available, they would be helpful in making a decision. Fast, but accurate would be 2-determining points. And then the ease of wading through the results and correcting and deleting, would be a 3rd. determining point. Has anyone had any experience with using any, or all 3 of these programs?
-Mike
 
Thanks for mentioning,. SongKong can quickly identify duplicates just using existing metadata but that relies on metadata being correct so is less accurate. SongKongs main task is Fix Songs and having used this to identify albums and added fingerprints (and MusicBrainz Ids) the Delete Duplicates function should run pretty quickly. Fix Songs can take a while to run because fingerprinting is cpu intensive, matching relies on using internet to match to database and if many changes found there is I/O required to write all the changes to your files. But Fix Songs can be run completely unattended on a music collection of any size, so works well if you just let it run overnight. On a reasonable modern computer with broadband connection expect about 5000 songs to be processed an hour, for an older low powered compute or nas this may go down to 1000 songs an hour.
 
Hi, just to note with SongKong that you can Fix Songs on your whole collection in **preview mode**, this does not require a license. This will create a report where it will accurately show you exactly what has been matched and what metadata has been added.
 
I understand where you are coming from but I respectfully disagree. In the simple case SongKong identifies folder of songs to tracks within the same album, then each song has a MB song Id, and MB album id added. Then with Delete Duplicates you can elect to find duplicate songs based on having the same song Id and same album Id (i.e you have the same album twice), or just song id (have same song but maybe on two completely different albums, e.g original and a compilation).
 
Although our 100% FLAC database is >10tb, it is in fairly good order in terms of metadata. When we began ripping over 20-years ago, in the intervening years, we learned a lot, especially the importance of creating accurate metadata
 
If your metadata are in good shape (for both of your libraries) and if you have been precocious and split each album in a separate folder, then imho your task will be much easier. And a software like SongKong should be able to create a nearly-faultless list of your duplicates.
 
Hi, you can run Delete Duplicates and generate a report. If you already have reasonable metadata you could just use the default of Same song and same album (metadata only) to run, this should find some duplicates you get an idea of the report created. Basically the report groups songs by album and show the duplicates songs and the one that is kept and the ones deleted.
 
In the options you can configure to either delete the duplicates or move them to a folder, and in the case of duplicates you can specify preferred deletion criteria to determine the song that should be kept and songs that should be deleted/moved.
 
You can run in Preview mode first to see the results, check the results and then run for real. But SongKong does not offer the ability to individually select each duplicate, it is designed to be be configured and then run, if you have many duplicates then checking each one manually is too time intensive. Although you could use my other software Jaikoz if you want to take that approach.
 
Hi, the short answer is the **Default** profile should work well enough, except possibly remove performer from the list of fields added due to Roon possibly not recognising performer and performer(instrument) as the same person - Roon, Artist, Artist details - SongKong Questions - SongKong and Jaikoz Music Tagger Community Forum
 
I need to do an extensive review of how Roon currently processes the metadata provided to it, this is not so easy since Roon doesnt document this in that much detail, and the processing is tagging format specific so it may handle a field in a Wav file okay, but not the equivalent field in a Flac file. Until I have done this I cannot offer you a definitive Roon mapping just now.
 
I want to back up my audio CD collection in flac format. How do I do this if I want to preserve the option to restore the original CD's (in case they get lost) in such a way that any CD's burned from the flac archives can be played in any ordinary CD player just like the original CD's?
 
The newly burned CD played fine in Amarok and XMMS on my laptop. It also played fine in an mp3 capable SONY psyc Walkman (which unfortunately doesn't have good sound quality), but it didn't play properly in a model 1995 Panasonic portable CD player (my favorite) nor in a Phillips shelf-unit CD changer. The former couldn't read track 1 but could play track 2 and all subsequent tracks. The latter could play track 1, but skipped and dropped on most other tracks. It also made a strange continuous whining noise that came from the player housing rather than through the speakers.
 
My favorite CD player, the old Panasonic that can't play track 1, may have stumbled over the presence on the CD of six folders that K3b created that precede track 1, i.e. the folders CDA, FLAC, Full CD, Information, MP3, and Ogg Vorbis. I'm not sure what they are for.
 
Is there something I'm doing wrong with K3b? Or is there some other way how I can accomplish what I set out to do, i.e. to backup my CD's in a space-saving lossless way on my HDD, while retaining the ability to fully reconstitute them if needed, in such a way that the reburned CD's would play on every garden-variety CD player, just like the original CD's?
 
And on top of that: are you sure your cd-players support playing CDR(W)'s? Some, especially older models, only read pressed audio cd's. You also might wanna try to write the cd at a lower speed to help your player recognize the disc.
 
I tried RubyRipper and Asunder. Both ripped at an incredibly slow speed at their default settings, i.e. 20-30 min for 60-70 min audio CD's. It's just not feasible backing up a large collection of CD's that way. K3b did it in 4-5 min and so did KAudioCreator.
 
1. The 1995 Panasonic player often has problems starting up a track, in particular track 1, which it will play only after seeking for 30-60 seconds (I was wrong in saying that it doesn't play track 1 at all). The same sometimes happens wi