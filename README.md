# paasio

The PaaS.io CLI. This is the command line interface to PaaS.io's Application Platform

paasio is based on VMware's default vmc implementation, but contains
several extensions to work with PaaS.io's core platform.

_Copyright 2012, PaaS.io, Inc.
Copyright 2010-2011, VMware, Inc. Licensed under the
MIT license, please see the LICENSE file.  All rights reserved._

    Usage: paasio [options] command [<args>] [command_options]
    Try 'paasio help [command]' or 'paasio help options' for more information.

    Currently available paasio commands are:

    Getting Started
      login  [email] [--email, --passwd]           Login
      info                                         System and account information

    Applications
      apps                                         List deployed applications

    Application Creation
      create [appname]                             Create a new application
      create [appname] --url                       Set the url for the application
      create [appname] --instances <N>             Set the expected number <N> of instances
      create [appname] --mem M                     Set the memory reservation for the application
      create [appname] --runtime RUNTIME           Set the runtime to use for the application
      create [appname] --debug [MODE]              Push application and start in a debug mode

    Application Operations
      start <appname>                              Start the application
      stop  <appname>                              Stop the application
      restart <appname>                            Restart the application
      delete <appname>                             Delete the application
      rename <appname> <newname>                   Rename the application

    Application Updates
      update <appname> [--path]                    Update the application bits
      mem <appname> [memsize]                      Update the memory reservation for an application
      map <appname> <url>                          Register the application to the url
      unmap <appname> <url>                        Unregister the application from the url
      instances <appname> <num|delta>              Scale the application instances up or down

    Application Information
      crashes <appname>                            List recent application crashes
      crashlogs <appname>                          Display log information for crashed applications
      logs <appname> [--all]                       Display log information for the application
      files <appname> [path] [--all]               Display directory listing or file download for path
      stats <appname>                              Display resource usage for the application
      instances <appname>                          List application instances

    Application Environment
      env <appname>                                List application environment variables
      env-add <appname> <variable[=]value>         Add an environment variable to an application
      env-del <appname> <variable>                 Delete an environment variable to an application

    Services
      services                                     Lists of services available and provisioned
      create-service <service> [--name,--bind]     Create a provisioned service
      create-service <service> <name>              Create a provisioned service and assign it <name>
      create-service <service> <name> <app>        Create a provisioned service and assign it <name>, and bind to <app>
      delete-service [servicename]                 Delete a provisioned service
      bind-service <servicename> <appname>         Bind a service to an application
      unbind-service <servicename> <appname>       Unbind service from the application
      clone-services <src-app> <dest-app>          Clone service bindings from <src-app> application to <dest-app>
      tunnel <servicename> [--port]                Create a local tunnel to a service
      tunnel <servicename> <clientcmd>             Create a local tunnel to a service and start a local client

    Administration
      user                                         Display user account information
      passwd                                       Change the password for the current user
      logout                                       Logs current user out of the target system
      add-user [--email, --passwd]                 Register a new user (requires admin privileges)
      delete-user <user>                            Delete a user and all apps and services (requires admin privileges)

    System
      runtimes                                     Display the supported runtimes of the target system
      frameworks                                   Display the recognized frameworks of the target system

    Misc
      aliases                                      List aliases
      alias <alias[=]command>                      Create an alias for a command
      unalias <alias>                              Remove an alias
      targets                                      List known targets and associated authorization tokens

    Help
      help [command]                               Get general help or help on a specific command
      help options                                 Get help on available options

## Simple Story (for Ruby apps)

    paasio login
    bundle package
    paasio push
