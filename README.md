CPU Stress and Logging Script for Ubuntu Server

This script sets up a system to stress test the CPU and log the system statistics using sar.
Usage
Run the setup.sh script to install the necessary dependencies, create the cpu_stress.sh file, and set up the crontab entries for automatic logging.

shell

$ ./setup.sh

    The script will run every time the system is rebooted.

    The system statistics will be logged to a file named sar.log in the same directory as the cpu_stress.sh file.

    To view a graph or diagram of the system statistics collected by sar, use the following command:

lua

$ sar -f /path/to/sar.log -u -s 08:00:00 -e 08:30:00 --plot > cpu_usage.png

Replace /path/to/sar.log with the actual path to your sar log file.

    To view a graph of the system statistics in the terminal over SSH, use the following command:

lua

$ sar -f /path/to/sar.log -u | gnuplot -e "set terminal dumb; plot '-' using 1:3 with lines title 'CPU Usage'"

You can adjust the plot settings and graph types by modifying the gnuplot options and commands. For example, you can change the terminal type to x11 to display the graph in a separate window or use different plot styles and colors.
