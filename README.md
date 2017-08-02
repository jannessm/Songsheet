# Songsheet
This project highlights all important aspects about the <code>.st</code> format and how to write a file like it.

Version: 1.1.0
 
### Overview
- [Tutorial](#tut)
- [Elements](#elem)
    - [Title](#title)
    - [Order](#order)
    - [Block](#block)
    - [Chord](#chord)
    - [Annotation](#ann)
- [kind of Markdown support](#mark)
- [future goals](#future)
<a name="tut"></a>

## Tutorial
A <code> *.st </code> file defines the structure of a song. Typically a song consist of different 
segments, we call them blocks.

Define a block like this:
    
    [Block : Verse 1]
    
You can call them whatever you want, but the way you call them they will be displayed in the final pdf.

In this Block we will add some lyrics with chords as follows:

    [Block : Verse 1]
    [Em7] Today is [G]gonna be the day
    That they're [Dsus4]gonna throw it back to [A7sus4]you

Each Chord is added in <code> [ ] </code> and will be align with the succeeding character.

Ok, now let's add some blocks:

    [Block : Verse 1]
    [Em7] Today is [G]gonna be the day
    That they're [Dsus4]gonna throw it back to [A7sus4]you
        
    [Block : Verse 2]
    [Em7] Back beat, the [G]word is on the street
    That the [Dsus4]fire in your heart is [A7sus4]out,
        
    [Block : Intro]
    [Em7] [G] [Dsus4] [A7sus4]
    
To use some blocks a few times add an order:
 
    [Order: Intro, Verse 1, Verse 2, Verse 1]
        
    [Block : Verse 1]
    [Em7] Today is [G]gonna be the day
    That they're [Dsus4]gonna throw it back to [A7sus4]you
        
    [Block : Verse 2]
    [Em7] Back beat, the [G]word is on the street
    That the [Dsus4]fire in your heart is [A7sus4]out,
        
    [Block : Intro]
    [Em7] [G] [Dsus4] [A7sus4]
 
 Of course it would be nice to have a headline with the title of the song.
 
    [Title: Wonderwall - Oasis]
        
    [Order: Intro, Verse 1, Verse 2, Verse 1]
        
    [Block : Verse 1]
    [Em7] Today is [G]gonna be the day
    That they're [Dsus4]gonna throw it back to [A7sus4]you
        
    [Block : Verse 2]
    [Em7] Back beat, the [G]word is on the street
    That the [Dsus4]fire in your heart is [A7sus4]out,
        
    [Block : Intro]
    [Em7] [G] [Dsus4] [A7sus4]
    
 Annotate your sheet
 
     [Title: Wonderwall - Oasis]
        
    [Order: Intro, Verse 1, Verse 2, Verse 1]
        
    [Block : Verse 1]
    [Em7] Today is [G]gonna be the day      | soft sounds | Alice solo
    That they're [Dsus4]gonna throw it back to [A7sus4]you
        
    [Block : Verse 2]
    [Em7] Back beat, the [G]word is on the street
    That the [Dsus4]fire in your heart is [A7sus4]out,
        
    [Block : Intro]
    [Em7] [G] [Dsus4] [A7sus4]

 If you want different annotations for each appearance seperate each annotation in the order of appearance by ; like
 this:

    [Em7] Today is [G]gonna be the day      | soft sounds ; acapella ; rock it | Alice solo

 Now you need three lines of code to create your PDF:
 
    from songsheet import SongsheetGen
    
    if __name__ == '__main__':
        gen = SongsheetGen('Wonderwall', 'Wonderwall.pdf')
        gen.gen()
        
 Done!
 <a name="elem"></a>
 
 
## Elements
 
 All available elements are documented here briefly.
 <a name="title"></a>
 
 
#### Title
    
    [title: Wonderwall]
 <a name="order"></a>
 
 
#### Order
    
    [order: block1, block2, block1]
 <a name="block"></a>
 
 
#### Block
    
    [block: ID]
    block_content
 <a name="chord"></a>
 
#### Chord
    
    Songtext blabla[Em] asfadfljk
 <a name="ann"></a>
 
#### Annotation
    
    fooooo | annotation_cell | another annotation_cell
 <a name="mark"></a>
 
 
 ## kind of Markdown support
 
 to highlight specific parts following command are supported:
 
 - \*text\* : *text*
 - \*\*text\*\* : **text**
 - \<r>text\<r> : red text
 - \<g>text\<g> : green text
 - \<b>text\<b> : blue text
 <a name="future"></a>
 
 ## Goals for future Versions
 
  - other layouts and fonts
  - annotation-cells title
  - song info (bpm, artist, ...)
  - created with songsheet footer 
  - page numbers
  - band logo support
  
  Please contact me for further Ideas ;).
  
