# Migration planning

Thank you for your patience while we have been completing the process for procuring and deploying SUNBIRD2,
the replacement for the existing SUNBIRD service.
We apologise that this is significantly later than planned,
primarily due to difficulties with the supply chain outside of our control.

We can now,
finally,
announce that
we are nearly ready to bring the SUNBIRD2 service into production
in the next few weeks.
While we cannot announce a final date for this yet,
please carefully read the below details about the migration process,
to avoid surprises later.

## Existing SUNBIRD service

The existing SUNBIRD service will shut down
when the new SUNBIRD2 service goes live.

## Users

All users at Swansea and Aberystwyth who have active institutional accounts
will be migrated,
as will all external users associated with projects
with an active project leader at Swansea or Aberystwyth.
Basically:
**if you are using SUNBIRD1 currently,
you should automatically receive an account on SUNBIRD2**.

## `/home` data

The home directories of all users to be migrated
will be copied to SUNBIRD2 in advance of the service becoming available.
Conversely,
if a user will not be migrated,
their data will not be copied.
**If you rely on data from a user who has left the University,
please get in touch with us**.

Project shared home directories
will likewise be copied across for all active projects.

## `/scratch` data

**Data in `/scratch` will not be copied to SUNBIRD2 automatically**.
We remind you that /scratch is intended
for short-term transient data during a project,
and that long-term data must be transferred off the machine
once it is no longer required there.

You will not be able to
transfer your entire `/scratch` directory directly to the new service.
As mentioned in previous updates,
**please transfer data no longer actively required on the system
to a suitable long-term storage platform**.
If there are data that you are mid-project with
and will need to keep working with on SUNBIRD2,
please get in touch to discuss details.

As the existing SUNBIRD service will be shut down when SUNBIRD2 goes live,
**please act now to transfer your data off this service**.
You will not be able to retrieve data from the existing SUNBIRD service
following its shutdown.

## AccelerateAI

While we are refreshing all CPU nodes,
the AccelerateAI GPU-enabled partition will remain available on SUNBIRD2.
To allow the nodes to be transferred from the old to the new machine,
**there will be a period of downtime for this partition**;
we apologise in advance for this inconvenience.

## Authentication and security

SUNBIRD2 will require two-factor authentication for all users.
This will be set up automatically on first login.
This will work with any common authenticator app
implementing the Time-based One Time Pad (TOTP) algorithm,
including Microsoft Authenticator.

As with any period of change,
there is a heightened risk of phishing and other cyberattacks.
We will be sending updates by email from sa2c-support@swansea.ac.uk.
**We will not send instructions or ask for credentials from any other email address,
and we will not phone or Zoom you,
without first confirming from the above address**.
As always, if you receive suspicious contacts from other addresses,
particularly outside of Swansea University,
please report them to the Cyber team.

## Software

SUNBIRD2 will have an entirely new software stack.
This will allow you to run newer application versions than on SUNBIRD.
You may however need to recompile your software to get started.
We will share more guidance on this closer to the time.

**If you have specific modules on SUNBIRD that you will require to be rebuilt for SUNBIRD2,
please check [the software listing](software.md),
and follow the instructions there if anything you require is missing**.

## Hardware specification

SUNBIRD2 comprises the following partitions:

- 46 standard-memory compute nodes, each with 128 CPU cores and 768GiB RAM
- 5 high-memory compute nodes, each with 128 CPU cores and 1.5TiB RAM
- 6 AccelerateAI nodes, each with 8 NVIDIA A100-40GB GPUs
    - One of these nodes is dedicated to interactive usage,
      with Multi-Instance GPU for rapid availability
- 1 AccelerateAI-H100 node, with 4 NVIDIA H100 GPUs
- 2 AccelerateAI-GH nodes,
  each with one NVIDIA Grace Hopper superchip
- Researcher-funded partitions migrated from SUNBIRD

If you have questions about the migration process or SUNBIRD2 more generally,
please don’t hesitate to get in touch.
