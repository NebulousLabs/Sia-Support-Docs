# How to set an environment variable

## Linux

To set an environment variable on Linux, enter the following command at a shell prompt, according to which shell you are using:

csh/tcsh: _variablevalue_ bash/ksh: _variable_=_value_

where variable is the name of the environment variable \(such as \) and value is the value you want to assign to the variable, \(such as \). To find out what environment variables are set, use the  command. To remove a variable from the environment, use the following commands:

csh/tcsh: _variable_bash/ksh: _variable_

## Windows

You can create or change environment variables in the Environment Variables dialog box. If you are adding to the PATH environment variable, or any environment variable that takes multiple values, you should separate each value with a semicolon \(;\).

### Windows 8 and Windows 10

**To open the Environment Variables dialog box:**

1. In Search, search for and then select: Edit environment variables for your account

**To create a new environment variable:**

1. In the User variables section, click New. The New User Variable dialog box opens.
2. Enter the name of the variable and its value, and click OK. The New User Variable dialog box closes, and the variable is added to the User variables section of the Environment Variables dialog box.
3. Click OK in the Environment Variables dialog box.

**To modify an existing environment variable:**

1. In the User variables section, select the environment variable you want to modify.
2. Click Edit. The Edit User Variable dialog box opens.
3. Change the value of the variable and click OK. The Edit User Variable dialog box closes, and the variable is updated in the User variables section of the Environment Variables dialog box.

When you have finished creating or editing environment variables, click OK in the Environment Variables dialog box to save the values.

### Windows 7

**To open the Environment Variables dialog box:**

1. Click Start, then click Control Panel. The Control Panel opens.
2. Click User Accounts.
3. Click User Accounts again.
4. In the Task side pane on the left, click Change my environment variables. The Environment Variables dialog box opens.

**To create a new environment variable:**

1. In the User variables section, click New. The New User Variable dialog box opens.
2. Enter the name of the variable and its value, and click OK. The New User Variable dialog box closes, and the variable is added to the User variables section of the Environment Variables dialog box.
3. Click OK in the Environment Variables dialog box.

**To modify an existing environment variable:**

1. In the User variables section, select the environment variable you want to modify.
2. Click Edit. The Edit User Variable dialog box opens.
3. Change the value of the variable and click OK. The Edit User Variable dialog box closes, and the variable is updated in the User variables section of the Environment Variables dialog box.

When you have finished creating or editing environment variables, click OK in the Environment Variables dialog box to save the values. You can then close the Control Panel.

## MacOS

To set an environment variable on Mac OSX, first open a terminal window.If you are setting the environment variable to run jobs from the command line, use the following command:

**export** _variable=value_

where variable is the name of the environment variable \(such as \) and value is the value you want to assign to the variable, \(such as \). You can find out which environment variables have been set with the command.

If you are setting the environment variable globally to use with applications, use the commands given below. The environment variables set by these commands are inherited by any shell or application.

### OS X 10.10

To set an environment variable, enter the following command:

**launchctl setenv** _variable "value"_

To find out if an environment variable is set, use the following command:

**launchctl getenv** _variable_

To clear an environment variable, use the following command:

**launchctl unsetenv** _variable_

### Newer version of MacOS

See [this article](https://apple.stackexchange.com/questions/106355/setting-the-system-wide-path-environment-variable-in-mavericks) for instructions on how to create a "plist" file to store system-wide environment variables in newer versions of macOS.

Thanks to [Schrodinger.com](https://www.schrodinger.com/kb/1842) for the content of this article.

