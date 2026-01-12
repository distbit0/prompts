pls add the specified files to chezmoi using the below commands:

Use this command if " $ENCRYPTION " is false, no, empty or something else clearly negative:

sudo chezmoi add --config /home/pimania/.config/chezmoi/chezmoi.toml --destination / --source /home/pimania/.local/share/chezmoi $FILE

or this one if " $ENCRYPTION " is ~true or something else clearly positive:

sudo chezmoi add --encrypt --config /home/pimania/.config/chezmoi/chezmoi.toml --destination / --source /home/pimania/.local/share/chezmoi $FILE

make sure to remove any /* from paths being added, and instead just end them with / . do not confirm this with me. just do it.

separate paths by spaces when passing them to the above commands


please do not actually try to run any commands, as they require sudo. rather pls just copy the final command to my clipboard using xclip -selection clipboard once you are done so I can run it myself.