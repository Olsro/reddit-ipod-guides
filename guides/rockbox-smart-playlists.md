# Rockbox does support smart playlists (and it's awesome)
*Date: 27 October 2024, last edited: 28 October 2024*

Hello Rockboxers :)

I've made today the discovery that Rockbox has a very powerful integrated system to build smart playlists dynamically using metadata of your songs.

You can also build new custom views, I found one here: [https://www.hwupgrade.it/forum/showthread.php?t=2219092&page=164&highlight=sansa+clip](https://www.hwupgrade.it/forum/showthread.php?t=2219092&page=164&highlight=sansa+clip) that is very interesting to show all albums by years from your album artists, so I provide here also in my example file to help you get started.

Adding new database virtual entries is pretty easy and then easily accessible through your "Custom" menu in your tagtree. I could replicate all my iTunes smart playlists fairly easily (after knowing what to do) and those views show the exact same amount of songs as their iTunes counterparts. The format to build playlists here is textual, but is just as powerful and even more customizable.

And since this way of creating view is "smart", it will auto-update when you will add new songs to the database which is crucial if you have a large music library or if you sync your music using iTunes (which cause often the same songs to be put into another path after syncing).

## Setting up the custom menu in your tagtree to your liking
Put this in a text file called **tagnavi_custom.config** in your **.rockbox** folder. This is the file you need to edit in order to add entries in your custom menu:

```
#! rockbox/tagbrowser/2.0
# ^ Version header must be the first line of every file

%format "fmt_artist_album_date"       "%04d %s %d.%02d. %s" year album discnum tracknum title

%menu_start "custom" "Custom"
"Artist > Album (date)" -> albumartist -> year ? year > "0" -> album -> title = "fmt_title"
"Artist & Album (date)" -> albumartist -> title = "fmt_artist_album_date"
```

Here is one example of how I could replicate most of my smart playlists:

```"SOUND HOLIC (all albums)" -> album ? albumartist ~ "SOUND HOLIC" -> title = "fmt_title"```

This code adds a new entry in the custom menu which means "list all albums and tracks belonging to all of the album artists that contains the name 'SOUND HOLIC'".

You can of course apply easily the same logic to any other metadata and even use "&" or "|" if you need more complex conditionals in your filter.

## Operators (very important to know):
| Operator | Clause
| :---: | :---:
| = | is
| == | is
| != | is not
| > | greater than
| >= | greater than or equals
| < | lower than
| <= | lower than or equals
| ~ | contains
| !~ | not contains
| ^ | begins with
| !^ | not begins with
| $ | ends with
| !$ | not ends with
| @^ | begins one of
| @$ | ends one of
| @ | one of

## Available tags
Here is a list of the available tags, it is also very important to have this near you when you're working at making a new smart playlist:
| Tag | Linkage
| :---: | :---:
| Lm | tag_virt_length_min
| Ls | tag_virt_length_sec
| Pm | tag_virt_playtime_min
| Ps | tag_virt_playtime_sec
| -> | menu_next
| ~> | menu_shuffle_songs
| ==> | menu_load
| year | tag_year
| album | tag_album
| genre | tag_genre
| title | tag_title
| %sort | var_sorttype
| artist | tag_artist
| length | tag_length
| rating | tag_rating
| %limit | var_limit
| %strip | var_strip
| bitrate | tag_bitrate
| comment | tag_comment
| discnum | tag_discnumber
| %format | var_format
| %reload | menu_reload
| filename | tag_filename
| basename | tag_virt_basename
| tracknum | tag_tracknumber
| composer | tag_composer
| grouping | tag_grouping
| entryage | tag_virt_entryage
| commitid | tag_commitid
| %include | var_include
| playcount | tag_playcount
| autoscore | tag_virt_autoscore
| lastplayed | tag_lastplayed
| lastoffset | tag_lastoffset
| %root_menu | var_rootmenu
| albumartist | tag_albumartist
| lastelapsed | tag_lastelapsed
| %menu_start | var_menu_start
| canonicalartist | tag_virt_canonicalartist

## Conclusion
I call this a "smart playlist" alternative to be less confusing and make a link with how iTunes works in your mind, but it is in fact way more powerful than just a way to build playlists; it can be used to create heavily personnalized (and conditional) filtered views.

As soon as you've understood the logic behind all of this, it is very fun and knowing everything that I share on this guide fixed one of my last frustration that remained with Rockbox compared to the Stock OS.
