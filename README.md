# CYB125-ai-final-project.
 
 ## About
 The script I am planning gathers the current configuration of the computer and then saves it to a JSON file, a snapshot, so it can be compared to other new devices and later snapshots to check for any changes/differences. Analysts will use it to compare snapshots and current configurations to establish a baseline and identify devices. It is important that, when new devices are introduced to networks, their baselines are set and checked against. It can also be used for future changes and to systematically check all devices for unauthorized changes. It is extremely helpful and important for keeping current and new systems secure and up to date with the defined secure baseline.

## Aproach
 The first source is the Windows Registry using the Python winreg module, which allows the script to get important system settings, operating system information, startup entries, and security configurations.The second source is Windows performance counter  which gets information about system performance such as CPU, memory, disk, and network usage. The third source is Windows command line utilities which give live information about accounts, running processes, installed software, services, and network activity. These three sources together give a more complete baseline snapshot of a system’s configuration and security.

## Data Dictionary
 snapshot = {
    "snapshot_metadata": {
        "timestamp": {},
        "hostname": {},
        "current_user": {},
        "elevated": {}
    },

    "system_identity": {
        "product_name": {},
        "release_id": {},
        "current_build": {},
        "registered_owner": {},
        "install_date": {}
    },

    "hardware_profile": {
        "cpu": {},
        "memory": {},
        "disk_drives": [],
        "bios": {}
    },

    "network_configuration": {
        "hostname": {},
        "ip_addresses": [],
        "mac_addresses": [],
        "default_gateway": {},
        "dns_servers": []
    },

    "listening_ports": [
        {
            "protocol": {},
            "local_address": {},
            "port": {},
            "process_id": {}
        }
    ],

    "local_user_accounts": [
        {
            "username": {},
            "enabled": {},
            "last_logon": {},
            "password_required": {}
        }
    ],

    "password_policy": {
        "minimum_password_length": {},
        "maximum_password_age": {},
        "minimum_password_age": {},
        "password_history_length": {},
        "lockout_threshold": {},
        "lockout_duration": {},
        "reset_lockout_counter": {}
    },

    "auto_start_services": [
        {
            "service_name": {},
            "display_name": {},
            "startup_type": {},
            "status": {}
        }
    ],

    "running_processes": [
        {
            "process_name": {},
            "process_id": {},
            "memory_usage": {}
        }
    ],

    "installed_software": [
        {
            "name": {},
            "version": {},
            "publisher": {},
            "install_date": {}
        }
    ],

    "installed_hotfixes": [
        {
            "hotfix_id": {},
            "description": {},
            "installed_on": {}
        }
    ],

    "persistence_locations": {
        "run_registry_keys": [],
        "startup_folder_items": [],
        "scheduled_tasks": []
    },

    "scheduled_tasks": [
        {
            "task_name": {},
            "status": {},
            "next_run_time": {}
        }
    ],

    "security_posture": {
        "firewall_enabled": {},
        "antivirus": {},
        "uac_enabled": {}
    },

    "performance_snapshot": {
        "cpu_usage": {},
        "memory_usage": {},
        "disk_usage": {},
        "network_usage": {}
    },

    "network_shares": [
        {
            "share_name": {},
            "path": {},
            "description": {}
        }
    ]
}

## Configuration Areas
snapshot_metadata – Keeps information such as when the snapshot was created, what user ran it, and what privileges.
system_identity – Keeps identifying info about the Windows installation such as the OS version, build number, and installation date.
hardware_profile – Gets information about the computer’s hardware such as the CPU, memory, BIOS, and storage devices.
network_configuration – Gets network settings such as IP addresses, MAC addresses, DNS servers, and default gateway information.
listening_ports – Lists all open network ports and the services currently listening for connections.
local_user_accounts – Gets information about local user accounts on the system including account status and login details.
password_policy – Gets password and account lockout settings to enforce security standards on the machine.
auto_start_services – Gets the services configured to automatically start when the operating system boots.
running_processes – Gets a snapshot of all processes currently running on the system.
installed_software – Gets applications installed on the system to identify authorized and unauthorized software.
installed_hotfixes – Finds installed Windows updates and security patches on the OS.
persistence_locations – Gets information about persistance mechanisms that malware could use to execute
scheduled_tasks – Finds scheduled tasks to automatically run programs/scripts at specific times.
security_posture – Gets important security settings such as firewall status, antivirus, and user account control.
performance_snapshot – Gets system performance information such as CPU, memory, disk, and network usage at the time of the snapshot, not just identyfing them unlike the profile
It is importnat to gether all of these becuase they identify key information and keep track of how they key information that was captured run to ensure it only has what it needs and runs as intended to detect any possible deviations.

## Strategy
My strategy to use the AI is to have it teach me and learn step by step what it is, to learn what each line of code individually does and the logic behind it, so I can apply it to what I already know and further improve upon it. I'll ask it to further describe the information we're collecting so I can better understand why it's important to gather that info and how it all goes together to create a baseline. I will review the code it provides myself to see if I spot anything off and test it myself to see if any errors occur, especially logic errors. I believe the first milestone will be very helpful because it helps set up the beginning information on how to get the information, which I can use similarly to get the rest of them, which is where I expect I'll need it less.

## Milestones
The project is structured around eight milestones, each one designed to produce a working
JSON file with an additional section implemented. The milestone structure isn't just a grading
convenience, it's a deliberate AI-collaboration pattern.
When students use AI well, they treat it like a pair programmer: they bring it small, well-scoped
problems, ask it to explain things rather than just produce things, and verify its answers against
an authoritative source (the textbook, the official Python docs, or their own running code). The
output is code they understand and could rewrite from scratch.
The eight-milestone structure exists to force the second pattern. Each milestone is small
enough that you can hold the whole thing in your head. Each milestone has a specific Python
concept attached to it, so you know what you're supposed to be learning. Each milestone has a
suggested AI prompt that asks for explanation, not code.
Your goal is not to finish the project as fast as possible. Your goal is to finish the project
understanding what you built. Those are different goals. The milestone structure pushes you
toward the second one. 
