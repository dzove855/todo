# TODO
A simple cli todo manager written in bash and use directory based format for saving tasks instead of a backend like json format or xml

Help:
```Usage: todo [d:p:i:s:h] ...

    Options:
        add:
            -d          Description
            -p          priority (high,medium,low)
            -i          Force id
        edit:
            -i          id
            -p          priority
            -d          Description
        done:
            -i          id
        ongoing:
            -i          id
        show:
            -i          id
        list:
            Default: Id orders from high priority to low, and from ongoing to created (Done will not be listed only if set)
            -p          Priority
            -s          state (done,ongoing,done)
        remove:
            -i          id

        -h      Help

    Environment Variables:
        NO_COLOR
        TODO_WORKINGDIR

    About
        This script will create the following directory tree:
            HOME/todo/{created,done,ongoing}/{high,medium,low}/ID/{description,content}
```

Examples:
```
Add new entry:
  todo add -p high -d "This is a simple description"  # $EDITOR will now open to write the todo tasks
  
List all entry's:
  todo list  # Only ongoing and created will be listed, to list also the tasks which are done, you need to use the -s option
  
Mark as done:
  todo done -i ID
  
Mark as ongoing:
  todo ongoing -i ID
   
Edit a task:
  todo edit -i ID  # $EDITOR will now open the task file, to change the description you need to reuse -d

Devtodo shortcuts to add in your .bashrc:
  alias tda="todo add"
  alias tdr="todo remove"
  alias tdl="todo list"
  alias tde="todo edit"
  alias tdd="todo done"
  alias tdo="todo ongoing"
  alias tds="todo show"
```

# Inspired
* devtodo v1
* birch (for directory based)
* add short commands
