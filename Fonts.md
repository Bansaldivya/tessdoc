# Fonts for Tesseract training

Tesseract training can use images made from text which was rendered with a list of fonts. Those fonts must be available on the host where the training process is running.

The required fonts are defined in [training/language-specific.sh](https://github.com/tesseract-ocr/tesseract/blob/master/training/language-specific.sh).

## Find Fonts

To find fonts already installed on your system  which will render a given training text, you can use the following command (change the language code and directory locations to match your setup). fontslist.txt will provide text that can be used in training/language-specific.sh.

```
text2image --find_fonts \
--fonts_dir /usr/share/fonts \
--text ../langdata/hin/hin.training_text \
--min_coverage .9  \
--outputbase ../langdata/hin/hin \
|& grep raw | sed -e 's/ :.*/" \\/g'  | sed -e 's/^/  "/' >../langdata/hin/fontslist.txt
```
The above will not work for Fraktur fonts, it will identify all Latin fonts also. Review the generated images and choose appropriate fonts.

## Font installation

### Debian

On Debian GNU Linux and similar distributions (Linux Mint, Ubuntu, ...),
the required fonts can be installed like that:

    # AMHARIC_FONTS (todo)
    # ANCIENT_GREEK_FONTS (todo)
    # ARABIC_FONTS (todo)
    # ARMENIAN_FONTS (todo)
    # BENGALI_FONTS (todo)
    # BURMESE_FONTS (todo)
    # CHI_SIM_FONTS (todo)
    # CHI_TRA_FONTS (todo)

    # DEVANAGARI_FONTS (see also external links below)
    apt-get install fonts-deva

    # EARLY_LATIN_FONTS (todo)
    # FRAKTUR_FONTS (todo)
    # GEORGIAN_FONTS (todo)
    # GREEK_FONTS (todo)
    # GUJARATI_FONTS (todo)
    # HEBREW_FONTS (todo)

    # JPN_FONTS (todo)
    apt-get install fonts-noto-cjk fonts-japanese-mincho.ttf fonts-takao-gothic fonts-vlgothic

    # KANNADA_FONTS (todo)
    # KHMER_FONTS (todo)
    # KOREAN_FONTS (todo)
    # KURDISH_FONTS (todo)
    # KYRGYZ_FONTS (todo)
    # LAOTHIAN_FONTS (todo)

    # LATIN_FONTS
    apt-get install fonts-dejavu gsfonts ttf-mscorefonts-installer

    # MALAYALAM_FONTS (todo)

    # NEOLATIN_FONTS (still incomplete)
    apt-get install fonts-ebgaramond fonts-gfs-didot fonts-gfs-didot-classic fonts-junicode

    # NORTH_AMERICAN_ABORIGINAL_FONTS (todo)
    # OLD_GEORGIAN_FONTS (todo)
    # ORIYA_FONTS (todo)
    # PERSIAN_FONTS (todo)
    # PUNJABI_FONTS (todo)
    # RUSSIAN_FONTS (todo)
    # SINHALA_FONTS (todo)
    # SYRIAC_FONTS (todo)
    # TAMIL_FONTS (todo)
    # TELUGU_FONTS (todo)
    # THAANA_FONTS (todo)
    # THAI_FONTS (todo)
    # TIBETAN_FONTS (todo)
    # VERTICAL_FONTS (todo)
    # VIETNAMESE_FONTS (todo)

The installed fonts are shown by the command `fc-list`. See also the [Debian wiki](https://wiki.debian.org/Fonts).

## Links

### Sources of (mostly free) fonts

#### Latin Fonts

* https://fontlibrary.org/en (GFS Bodoni)
* https://fonts.google.com/
* http://iginomarini.com/fell/the-revival-fonts/
* http://scholarsfonts.net/ (Cardo)
* http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=FontDownloads (SIL Fonts)
* http://www.ctan.org/tex-archive/fonts (GFS Bodoni)
* http://www.steffmann.de/wordpress/test-2/

#### Devanagari Fonts

* [Aksharayogini2](http://aksharyogini.sudhanwa.com/download/Aksharyogini2Normal.ttf)
* [AksharayoginiBoldItalic](http://aksharyogini.sudhanwa.com/download/AksharyoginiBoldItalic.ttf)
* [AksharayoginiBold](http://aksharyogini.sudhanwa.com/download/AksharyoginiBold.ttf)
* [AksharayoginiItalic](http://aksharyogini.sudhanwa.com/download/AksharyoginiItalic.ttf)
* [Aksharayogini](http://aksharyogini.sudhanwa.com/download/AksharyoginiNormal.ttf)
* [AnnapurnaSIL](http://software.sil.org/downloads/d/annapurna/AnnapurnaSIL-1.201.zip)
* [CDAC-Surekh Bold](http://biharvidhanparishad.gov.in/Fonts/CDACSRBT.TTF)
* [CDAC-Surekh Normal](http://biharvidhanparishad.gov.in/Fonts/CDACSRNT.TTF)
* [CDAC-Yogesh Bold](http://biharvidhanparishad.gov.in/Fonts/CDACOTYGB.TTF)
* [CDAC-Yogesh Italic](http://biharvidhanparishad.gov.in/Fonts/CDACYGIT.TTF)
* [CDAC-Yogesh Normal](http://biharvidhanparishad.gov.in/Fonts/CDACOTYGN.TTF)
* [Chandas](http://www.sanskritweb.net/cakram/chandas.ttf)
* [Lohit Devanagari](https://releases.pagure.org/lohit/Lohit-Devanagari.ttf)
* [Nakula](http://bombay.indology.info/software/fonts/devanagari/nakula.ttf)
* [Sahadeva](http://bombay.indology.info/software/fonts/devanagari/sahadeva.ttf)
* [Sanskrit2003](http://www.sanskritweb.net/itrans/sanskrit2003.zip)
* [Santipur OT](http://www.sanskritweb.net/itrans/santipurot.zip)
* [Sharad76](http://www.setuadvertising.com/sharad76/)
* [Shobhika](https://github.com/Sandhi-IITBombay/Shobhika/releases/)
* [Shree-DV0726-OT](http://biharvidhanparishad.gov.in/Fonts/SHREE-DV0726-OT.TTF)
* [Siddhanta](https://sites.google.com/site/bayaryn/siddhanta-variations.zip?attredirects=0)
* [Uttara](http://www.sanskritweb.net/cakram/uttara.ttf)
* [Yashomudra Fonts](https://github.com/RajyaMarathiVikasSanstha/Yashomudra/tree/master/TTF%20Files)
* [Google Devanagari Fonts](https://fonts.google.com/?subset=devanagari)
* [Linked from Bihar Vidhan Parishad](http://biharvidhanparishad.gov.in/HindiFonts.htm)
* [Linked from bih.nic.in](http://industries.bih.nic.in/HindiFonts.htm)

#### Fraktur Fonts

* http://unifraktur.sourceforge.net/maguntia.html (UnifrakturMaguntia)
* http://www.orbitals.com/self/ligature/ligature.htm (Wyld)
* https://www.fontyukle.net/de/1,Walbaum
* http://de.ffonts.net/Walbaum-Fraktur.font.download
* http://www.1001fonts.com/fraktur-fonts.html
* http://www.dafont.com/fette-unz-fraktur.font
* http://www.1001freefonts.com/fette_fraktur.font

#### Hebrew Fonts
* [A list of Hebrew fonts from the Open Siddur Project](http://opensiddur.org/tools/fonts/)

### More information on fonts

* https://en.wikipedia.org/wiki/Fraktur
* http://www.orbitals.com/self/ligature/ligature.htm 18th Century Ligatures and Fonts
* http://www.steffmann.de/wordpress/ (German)