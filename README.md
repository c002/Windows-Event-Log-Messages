# Windows Event Log Messages

The Windows Event Log Messages (WELM) tool retrieves the definitions of Windows Event Log messages embedded in binaries. The tool's output can be used to create an exhaustive list of event information for an operating system.

The tool was initially developed to aid in writing the [Spotting the Adversary with Windows Event Log Monitoring](https://www.iad.gov/iad/library/ia-guidance/security-configuration/applications/spotting-the-adversary-with-windows-event-log-monitoring.cfm) paper but has proven useful in a number of scenarios:

* Determining if there is an event that captures specific data of interest.
* Diffing event changes between operating system releases.
* Diffing event changes between operating system patch levels (more common in Windows 10).
* Documenting event specific informational fields and their data types which is useful for enriching event collection and analysis systems.
* Determining default states for logs and sources (enabled/disabled, max size, rotation policy, permissions, etc).
* Observing event system changes over time.

## Documentation

For more information see:

* [Building WELM](./docs/Building%20WELM.md) - how to build WELM.
* [Running WELM](./docs/Running%20WELM.md)  -  how to run WELM.
* [Retrieving Data](./docs/Retrieving%20Data.md) - how retrieve event data with WELM.
* [Datasets](./docs/Datasets.md) - data retrieved with WELM.

## Data

Retrieved data is available as a dated (YYYMMDD) zip file attachment on the [latest release](https://github.com/nsacyber/Windows-Event-Log-Messages/releases) organized by operating system version and architecture. Expanding the dated zip file attachment results in a number of folders that corresponding to Windows operating system releases along with the architecture version. See the [Datasets](./docs/Datasets.md) page for more information about each folder and its corresponding media.

Most of the operating system folders contain two folders: **welm** and **wevtutil**. These folders were generated by using a [batch file](https://github.com/nsacyber/Windows-Event-Log-Messages/blob/master/welm/welm.bat) that calls WELM and wevutil. The **welm** folder contains files generated by the WELM tool. The **wevtutil** folder contains files generated by using wevutil to dump all log and publisher information. Most users will be interested in the **events.csv**, **logs.csv**, and **providers.csv** files inside the the welm folder for each operating system.

## Links

* [Spotting the Adversary with Windows Event Log Monitoring](https://apps.nsa.gov/iaarchive/library/reports/spotting-the-adversary-with-windows-event-log-monitoring.cfm)
* [Event-Forwarding-Guidance](https://github.com/nsacyber/Event-Forwarding-Guidance) repository for the Spotting the Adversary with Windows Event Log Monitoring paper
* [Windows 10 and Server 2016 security auditing and monitoring reference](https://www.microsoft.com/en-us/download/details.aspx?id=52630)

## License

See [License](LICENSE.md).

## Disclaimer

See [Disclaimer](DISCLAIMER.md).