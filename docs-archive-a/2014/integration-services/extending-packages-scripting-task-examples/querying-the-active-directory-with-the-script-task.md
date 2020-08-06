---
title: Interrogation d’Active Directory avec la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Active Directory access
- SSIS Script task, Active Directory access
- Script task [Integration Services], examples
- Active Directory [Integration Services]
ms.assetid: a88fefbb-9ea2-4a86-b836-e71315bac68e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 624aa56289b9cab9174882b586a37e5d0de7ca9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601615"
---
# <a name="querying-the-active-directory-with-the-script-task"></a><span data-ttu-id="c1269-102">Interrogation d'Active Directory avec la tâche de script</span><span class="sxs-lookup"><span data-stu-id="c1269-102">Querying the Active Directory with the Script Task</span></span>
  <span data-ttu-id="c1269-103">Les applications de traitement des données d'entreprise, telles que les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], ont souvent besoin de traiter des données différemment selon l'échelon, le poste ou d'autres caractéristiques des employés stockés dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c1269-103">Enterprise data processing applications, such as [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, often need to process data differently based on the rank, job title, or other characteristics of employees stored in Active Directory.</span></span> <span data-ttu-id="c1269-104">Active Directory est un service d’annuaire [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows qui fournit un magasin centralisé de métadonnées, non seulement sur les utilisateurs, mais aussi sur d’autres ressources organisationnelles, comme les ordinateurs et les imprimantes.</span><span class="sxs-lookup"><span data-stu-id="c1269-104">Active Directory is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows directory service that provides a centralized store of metadata, not only about users, but also about other organizational assets such as computers and printers.</span></span> <span data-ttu-id="c1269-105">L'espace de noms `System.DirectoryServices` dans le Microsoft .NET Framework fournit des classes à utiliser avec Active Directory, pour vous aider à diriger le flux de travail du traitement des données selon les informations qu'il stocke.</span><span class="sxs-lookup"><span data-stu-id="c1269-105">The `System.DirectoryServices` namespace in the Microsoft .NET Framework provides classes for working with Active Directory, to help you direct data processing workflow based on the information that it stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1269-106">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="c1269-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="c1269-107">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="c1269-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="c1269-108">Description</span><span class="sxs-lookup"><span data-stu-id="c1269-108">Description</span></span>  
 <span data-ttu-id="c1269-109">L'exemple suivant extrait le nom, le titre et le numéro de téléphone d'un employé dans Active Directory selon la valeur de la variable `email`, laquelle contient l'adresse de messagerie de l'employé.</span><span class="sxs-lookup"><span data-stu-id="c1269-109">The following example retrieves an employee's name, title, and phone number from Active Directory based on the value of the `email` variable, which contains the e-mail address of the employee.</span></span> <span data-ttu-id="c1269-110">Les contraintes de précédence dans le package peuvent utiliser les informations extraites pour déterminer, par exemple, s'il faut envoyer un message électronique de priorité basse ou une page prioritaire, selon le poste de l'employé.</span><span class="sxs-lookup"><span data-stu-id="c1269-110">Precedence constraints in the package can use the retrieved information to determine, for example, whether to send a low-priority e-mail message or a high-priority page, based on the job title of the employee.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="c1269-111">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="c1269-111">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="c1269-112">Créez les trois variables de chaîne `email`, `name` et `title`.</span><span class="sxs-lookup"><span data-stu-id="c1269-112">Create the three string variables `email`, `name`, and `title`.</span></span> <span data-ttu-id="c1269-113">Entrez une adresse de messagerie professionnelle valide en tant que valeur de la variable `email`.</span><span class="sxs-lookup"><span data-stu-id="c1269-113">Enter a valid corporate email address as the value of the `email` variable.</span></span>  
  
2.  <span data-ttu-id="c1269-114">Dans la page **script** de l **'éditeur de tâche de script**, ajoutez la `email` variable à la `ReadOnlyVariables` propriété.</span><span class="sxs-lookup"><span data-stu-id="c1269-114">On the **Script** page of the **Script Task Editor**, add the `email` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="c1269-115">Ajoutez les variables `name` et `title` à la propriété `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="c1269-115">Add the `name` and `title` variables to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="c1269-116">Dans le projet de script, ajoutez une référence à l' `System.DirectoryServices` espace de noms.</span><span class="sxs-lookup"><span data-stu-id="c1269-116">In the script project, add a reference to the `System.DirectoryServices` namespace.</span></span>  
  
5.  <span data-ttu-id="c1269-117">.</span><span class="sxs-lookup"><span data-stu-id="c1269-117">.</span></span> <span data-ttu-id="c1269-118">Dans votre code, utilisez une instruction `Imports` pour importer l'espace de noms `DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="c1269-118">In your code, use an `Imports` statement to import the `DirectoryServices` namespace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1269-119">Pour exécuter ce script correctement, votre entreprise doit utiliser Active Directory sur son réseau et stocker les informations sur l'employé que cet exemple utilise.</span><span class="sxs-lookup"><span data-stu-id="c1269-119">To run this script successfully, your company must be using Active Directory on its network and storing the employee information that this example uses.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c1269-120">Code</span><span class="sxs-lookup"><span data-stu-id="c1269-120">Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim directory As DirectoryServices.DirectorySearcher  
    Dim result As DirectoryServices.SearchResult  
    Dim email As String  
  
    email = Dts.Variables("email").Value.ToString  
  
    Try  
        directory = New _  
            DirectoryServices.DirectorySearcher("(mail=" & email & ")")  
        result = directory.FindOne  
        Dts.Variables("name").Value = _  
            result.Properties("displayname").ToString  
        Dts.Variables("title").Value = _  
            result.Properties("title").ToString  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
public void Main()  
{  
    //  
    DirectorySearcher directory;  
    SearchResult result;  
    string email;  
  
    email = (string)Dts.Variables["email"].Value;  
  
    try  
    {  
        directory = new DirectorySearcher("(mail=" + email + ")");  
        result = directory.FindOne();  
        Dts.Variables["name"].Value = result.Properties["displayname"].ToString();  
        Dts.Variables["title"].Value = result.Properties["title"].ToString();  
        Dts.TaskResult = (int)ScriptResults.Success;  
    }  
    catch (Exception ex)  
    {  
        Dts.Events.FireError(0, "Script Task Example", ex.Message + "\n" + ex.StackTrace, String.Empty, 0);  
        Dts.TaskResult = (int)ScriptResults.Failure;  
    }  
  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="c1269-121">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="c1269-121">External Resources</span></span>  
  
-   <span data-ttu-id="c1269-122">Article technique, [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588), sur social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c1269-122">Technical article, [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588), on social.technet.microsoft.com</span></span>  
  
<span data-ttu-id="c1269-123">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c1269-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c1269-124">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="c1269-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c1269-125">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="c1269-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c1269-126">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="c1269-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
