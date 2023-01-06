---
description: Adjust your Pterodactyl to allow using Spectre.
---

# 🦇 Pterodactyl

_by Peter#3261_

__

You will need setup port allocation first on the respective node for your FiveM server

<figure><img src="../.gitbook/assets/port_alo_perto.png" alt=""><figcaption><p>Port allocation (Sample ip)</p></figcaption></figure>

If you have modified your Spectre port you will need to ensure you put the respective port in the “Ports” section, once you’ve filled this in Submit this.

Next, navigate to your “Server” and under “Build Configuration”.

<figure><img src="../.gitbook/assets/port_assign_perto.png" alt=""><figcaption><p>Assign port</p></figcaption></figure>

You will want to select the Spectre Panel port as an assigned additional port, once added click update build configuration

Once you’ve done this you **MUST** restart the full docker server container.

![](<../.gitbook/assets/image (1).png>)

Once you restart the server you can continue on with the normal Spectre setup process and you will be able to visit <mark style="color:blue;">http://IP:PORT</mark>.\