.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _openssh_powershell:

Installiere OpenSSH über Powershell
=======================================

Wenn du dich mit ``ssh <username>@<hostname>.local`` (oder ``ssh <username>@<IP address>``) mit deinem Raspberry Pi verbinden möchtest, aber die folgende Fehlermeldung angezeigt wird:

    .. code-block::

        ssh: The term 'ssh' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the
        spelling of the name, or if a path was included, verify that the path is correct and try again.


bedeutet das, dass dein Windows-System zu alt ist und `OpenSSH <https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui>`_ nicht vorinstalliert wurde. Du musst es daher manuell nach der folgenden Anleitung installieren.  

#. Gib ``powershell`` in das Suchfeld deines Windows-Desktops ein, klicke mit der rechten Maustaste auf ``Windows PowerShell`` und wähle im erscheinenden Menü **Als Administrator ausführen**.  

    .. image:: img/powershell_ssh.png
        :align: center

#. Führe den folgenden Befehl aus, um ``OpenSSH.Client`` zu installieren:  

    .. code-block::

        Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0

#. Nach der Installation erhältst du eine Ausgabe wie diese:  

    .. code-block::

        Path          :
        Online        : True
        RestartNeeded : False

#. Überprüfe die Installation mit folgendem Befehl:  

    .. code-block::

        Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'

#. Nun sollte angezeigt werden, dass ``OpenSSH.Client`` erfolgreich installiert wurde:  

    .. code-block::

        Name  : OpenSSH.Client~~~~0.0.1.0
        State : Installed

        Name  : OpenSSH.Server~~~~0.0.1.0
        State : NotPresent

    .. warning:: 
        Wenn diese Ausgabe nicht erscheint, bedeutet das, dass dein Windows-System weiterhin zu alt ist. In diesem Fall empfehlen wir, ein Drittanbieter-SSH-Tool wie :ref:`login_windows` zu verwenden.  

#. Starte PowerShell anschließend neu und führe es erneut als Administrator aus. Nun kannst du dich mit dem ``ssh``-Befehl bei deinem Raspberry Pi anmelden. Dabei wirst du nach dem Passwort gefragt, das du zuvor eingerichtet hast.  

    .. image:: img/powershell_login.png