---
title: Envoi d’un message électronique HTML à l’aide de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Send Mail task [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], HTML mail message
ms.assetid: dd2b1eef-b04f-4946-87ab-7bc56bb525ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c1a967b52a84e1ff9c2e54c48e40f4d149b2dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695860"
---
# <a name="sending-an-html-mail-message-with-the-script-task"></a><span data-ttu-id="36094-102">Envoi d'un message électronique HTML à l'aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="36094-102">Sending an HTML Mail Message with the Script Task</span></span>
  <span data-ttu-id="36094-103">La tâche SendMail de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] prend uniquement en charge les messages électroniques au format texte brut.</span><span class="sxs-lookup"><span data-stu-id="36094-103">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] SendMail task only supports mail messages in plain text format.</span></span> <span data-ttu-id="36094-104">Toutefois, vous pouver envoyer facilement des messages électroniques HTML en utilisant la tâche de script et les fonctionnalités de messagerie du .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="36094-104">However you can easily send HTML mail messages by using the Script task and the mail capabilities of the .NET Framework.</span></span>

> [!NOTE]
>  <span data-ttu-id="36094-105">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="36094-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="36094-106">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="36094-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="36094-107">Description</span><span class="sxs-lookup"><span data-stu-id="36094-107">Description</span></span>
 <span data-ttu-id="36094-108">L'exemple suivant utilise l'espace de noms `System.Net.Mail` pour configurer et envoyer un message électronique HTML.</span><span class="sxs-lookup"><span data-stu-id="36094-108">The following example uses the `System.Net.Mail` namespace to configure and send an HTML mail message.</span></span> <span data-ttu-id="36094-109">Le script obtient le destinataire, l'expéditeur, l'objet et le corps du message électronique à partir de variables du package, les utilise pour créer un nouveau `MailMessag`e et définit sa propriété `IsBodyHtml` sur `True`.</span><span class="sxs-lookup"><span data-stu-id="36094-109">The script obtains the To, From, Subject, and body of the e-mail from package variables, uses them to create a new `MailMessag`e, and sets its `IsBodyHtml` property to `True`.</span></span> <span data-ttu-id="36094-110">Ensuite, il obtient le nom du serveur SMTP auprès d'une autre variable du package, initialise une instance de `System.Net.Mail.SmtpClient` et appelle sa méthode `Send` pour envoyer le message HTML.</span><span class="sxs-lookup"><span data-stu-id="36094-110">Then it obtains the SMTP server name from another package variable, initializes an instance of `System.Net.Mail.SmtpClient`, and calls its `Send` method to send the HTML message.</span></span> <span data-ttu-id="36094-111">L'exemple encapsule la fonctionnalité d'envoi du message dans une sous-routine susceptible d'être réutilisée dans d'autres scripts.</span><span class="sxs-lookup"><span data-stu-id="36094-111">The sample encapsulates the message sending functionality in a subroutine that could be reused in other scripts.</span></span>

#### <a name="to-configure-this-script-task-example-without-an-smtp-connection-manager"></a><span data-ttu-id="36094-112">Pour configurer cet exemple de tâche de script sans gestionnaire de connexions SMTP</span><span class="sxs-lookup"><span data-stu-id="36094-112">To configure this Script Task example without an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="36094-113">Créez des variables chaîne nommées `HtmlEmailTo`, `HtmlEmailFrom` et `HtmlEmailSubject`, puis attribuez-leur des valeurs appropriées à un message de test valide.</span><span class="sxs-lookup"><span data-stu-id="36094-113">Create string variables named `HtmlEmailTo`, `HtmlEmailFrom`, and `HtmlEmailSubject` and assign appropriate values to them for a valid test message.</span></span>

2.  <span data-ttu-id="36094-114">Créez une variable chaîne nommée `HtmlEmailBody` et attribuez-lui une chaîne de balise HTML.</span><span class="sxs-lookup"><span data-stu-id="36094-114">Create a string variable named `HtmlEmailBody` and assign a string of HTML markup to it.</span></span> <span data-ttu-id="36094-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="36094-115">For example:</span></span>

    ```
    <html><body><h1>Testing</h1><p>This is a <b>test</b> message.</p></body></html>
    ```

3.  <span data-ttu-id="36094-116">Créez une variable chaîne nommée `HtmlEmailServer` et attribuez le nom d'un serveur SMTP disponible qui accepte des messages sortants anonymes.</span><span class="sxs-lookup"><span data-stu-id="36094-116">Create a string variable named `HtmlEmailServer` and assign the name of an available SMTP server that accepts anonymous outgoing messages.</span></span>

4.  <span data-ttu-id="36094-117">Attribuez ces cinq variables à la propriété **ReadOnlyVariables** d’une nouvelle tâche de script.</span><span class="sxs-lookup"><span data-stu-id="36094-117">Assign all five of these variables to the **ReadOnlyVariables** property of a new Script task.</span></span>

5.  <span data-ttu-id="36094-118">Importez les espaces de noms `System.Net` et `System.Net.Mail` dans votre code.</span><span class="sxs-lookup"><span data-stu-id="36094-118">Import the `System.Net` and `System.Net.Mail` namespaces into your code.</span></span>

 <span data-ttu-id="36094-119">L'exemple de code de cette rubrique obtient le nom du serveur SMTP auprès d'une variable du package.</span><span class="sxs-lookup"><span data-stu-id="36094-119">The sample code in this topic obtains the SMTP server name from a package variable.</span></span> <span data-ttu-id="36094-120">Toutefois, vous pourriez également exploiter un gestionnaire de connexions SMTP pour encapsuler les informations de connexion, puis extraire le nom du serveur du gestionnaire de connexions dans votre code.</span><span class="sxs-lookup"><span data-stu-id="36094-120">However, you could also take advantage of an SMTP connection manager to encapsulate the connection information, and extract the server name from the connection manager in your code.</span></span> <span data-ttu-id="36094-121">La méthode <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> du gestionnaire de connexions SMTP renvoie une chaîne au format suivant :</span><span class="sxs-lookup"><span data-stu-id="36094-121">The <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> method of the SMTP connection manager returns a string in the following format:</span></span>

 `SmtpServer=smtphost;UseWindowsAuthentication=False;EnableSsl=False;`

 <span data-ttu-id="36094-122">Vous pouvez utiliser la méthode `String.Split` pour séparer cette liste d'arguments en un tableau de chaînes individuelles à chaque point-virgule (;) ou signe égal (=), puis extraire le deuxième argument (indice 1) du tableau en tant que nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="36094-122">You can use the `String.Split` method to separate this argument list into an array of individual strings at each semicolon (;) or equal sign (=), and then extract the second argument (subscript 1) from the array as the server name.</span></span>

#### <a name="to-configure-this-script-task-example-with-an-smtp-connection-manager"></a><span data-ttu-id="36094-123">Pour configurer cet exemple de tâche de script avec un gestionnaire de connexions SMTP</span><span class="sxs-lookup"><span data-stu-id="36094-123">To configure this Script Task example with an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="36094-124">Modifiez la tâche de script configurée précédemment en supprimant la variable `HtmlEmailServer` de la liste de la propriété **ReadOnlyVariables**.</span><span class="sxs-lookup"><span data-stu-id="36094-124">Modify the Script task configured earlier by removing the `HtmlEmailServer` variable from the list of **ReadOnlyVariables**.</span></span>

2.  <span data-ttu-id="36094-125">Remplacez la ligne de code qui obtient le nom du serveur :</span><span class="sxs-lookup"><span data-stu-id="36094-125">Replace the line of code that obtains the server name:</span></span>

    ```
    Dim smtpServer As String = _
      Dts.Variables("HtmlEmailServer").Value.ToString
    ```

     <span data-ttu-id="36094-126">par les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="36094-126">with the following lines:</span></span>

    ```
    Dim smtpConnectionString As String = _
      DirectCast(Dts.Connections("SMTP Connection Manager").AcquireConnection(Dts.Transaction), String)
    Dim smtpServer As String = _
      smtpConnectionString.Split(New Char() {"="c, ";"c})(1)
    ```

## <a name="code"></a><span data-ttu-id="36094-127">Code</span><span class="sxs-lookup"><span data-stu-id="36094-127">Code</span></span>

```vb
Public Sub Main()

  Dim htmlMessageTo As String = _
    Dts.Variables("HtmlEmailTo").Value.ToString
  Dim htmlMessageFrom As String = _
    Dts.Variables("HtmlEmailFrom").Value.ToString
  Dim htmlMessageSubject As String = _
    Dts.Variables("HtmlEmailSubject").Value.ToString
  Dim htmlMessageBody As String = _
    Dts.Variables("HtmlEmailBody").Value.ToString
  Dim smtpServer As String = _
    Dts.Variables("HtmlEmailServer").Value.ToString

  SendMailMessage( _
      htmlMessageTo, htmlMessageFrom, _
      htmlMessageSubject, htmlMessageBody, _
      True, smtpServer)

  Dts.TaskResult = ScriptResults.Success

End Sub

Private Sub SendMailMessage( _
    ByVal SendTo As String, ByVal From As String, _
    ByVal Subject As String, ByVal Body As String, _
    ByVal IsBodyHtml As Boolean, ByVal Server As String)

  Dim htmlMessage As MailMessage
  Dim mySmtpClient As SmtpClient

  htmlMessage = New MailMessage( _
    SendTo, From, Subject, Body)
  htmlMessage.IsBodyHtml = IsBodyHtml

  mySmtpClient = New SmtpClient(Server)
  mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials
  mySmtpClient.Send(htmlMessage)

End Sub
```

```csharp
public void Main()
        {

            string htmlMessageTo = Dts.Variables["HtmlEmailTo"].Value.ToString();
            string htmlMessageFrom = Dts.Variables["HtmlEmailFrom"].Value.ToString();
            string htmlMessageSubject = Dts.Variables["HtmlEmailSubject"].Value.ToString();
            string htmlMessageBody = Dts.Variables["HtmlEmailBody"].Value.ToString();
            string smtpServer = Dts.Variables["HtmlEmailServer"].Value.ToString();

            SendMailMessage(htmlMessageTo, htmlMessageFrom, htmlMessageSubject, htmlMessageBody, true, smtpServer);

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private void SendMailMessage(string SendTo, string From, string Subject, string Body, bool IsBodyHtml, string Server)
        {

            MailMessage htmlMessage;
            SmtpClient mySmtpClient;

            htmlMessage = new MailMessage(SendTo, From, Subject, Body);
            htmlMessage.IsBodyHtml = IsBodyHtml;

            mySmtpClient = new SmtpClient(Server);
            mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials;
            mySmtpClient.Send(htmlMessage);

        }
```

<span data-ttu-id="36094-128">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="36094-128">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="36094-129">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="36094-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="36094-130">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="36094-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="36094-131">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="36094-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="36094-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="36094-132">See Also</span></span>
 [<span data-ttu-id="36094-133">Tache Envoyer un message</span><span class="sxs-lookup"><span data-stu-id="36094-133">Send Mail Task</span></span>](../control-flow/send-mail-task.md)


