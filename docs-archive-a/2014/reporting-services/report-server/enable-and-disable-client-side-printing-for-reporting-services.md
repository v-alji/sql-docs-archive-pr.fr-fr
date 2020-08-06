---
title: Activer et désactiver l’impression côté client pour Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0e709c96-7517-4547-8ef6-5632f8118524
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 031a7cd9b5da07b03b76b6bf49db63572a8fe546
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611533"
---
# <a name="enable-and-disable-client-side-printing-for-reporting-services"></a><span data-ttu-id="7d51a-102">Activer et désactiver l'impression côté client pour Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7d51a-102">Enable and Disable Client-Side Printing for Reporting Services</span></span>
  <span data-ttu-id="7d51a-103">Le [!INCLUDE[msCoName](../../includes/msconame-md.md)] contrôle ActiveX, **RSClientPrint**, permet l’impression côté client pour les rapports affichés dans un navigateur.</span><span class="sxs-lookup"><span data-stu-id="7d51a-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX control, **RSClientPrint**, provides client-side printing for reports viewed in a browser.</span></span> <span data-ttu-id="7d51a-104">Le contrôle affiche une boîte de dialogue d'impression personnalisée qui prend en charge des fonctionnalités communes à d'autres boîtes de dialogue d'impression.</span><span class="sxs-lookup"><span data-stu-id="7d51a-104">The control displays a custom print dialog box that supports features common to other print dialog boxes.</span></span> <span data-ttu-id="7d51a-105">Les fonctionnalités incluent l'aperçu avant impression, les sélections de page pour spécifier des pages et des plages spécifiques, les marges des pages, et l'orientation.</span><span class="sxs-lookup"><span data-stu-id="7d51a-105">The features include print preview, page selections for specifying specific pages and ranges, page margins, and orientation.</span></span> <span data-ttu-id="7d51a-106">Bien que l'impression côté client soit activée par défaut, vous pouvez désactiver cette fonctionnalité pour l'empêcher d'être utilisée.</span><span class="sxs-lookup"><span data-stu-id="7d51a-106">Although client-side printing is enabled by default, you can disable the feature to prevent it from being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d51a-107">Des autorisations d'administrateur sont nécessaires pour le téléchargement des contrôles ActiveX.</span><span class="sxs-lookup"><span data-stu-id="7d51a-107">Downloading ActiveX controls requires administrator permissions.</span></span>  
  
## <a name="downloading-the-activex-control"></a><span data-ttu-id="7d51a-108">Téléchargement du contrôle ActiveX</span><span class="sxs-lookup"><span data-stu-id="7d51a-108">Downloading the ActiveX Control</span></span>  
 <span data-ttu-id="7d51a-109">Chaque utilisateur souhaitant utiliser la fonctionnalité d'impression doit télécharger et installer le contrôle ActiveX qui permet l'impression côté client.</span><span class="sxs-lookup"><span data-stu-id="7d51a-109">Each user who wants to use the print feature must download and install the ActiveX control that provides client print functionality.</span></span> <span data-ttu-id="7d51a-110">La première fois qu’un utilisateur clique sur l’icône de l' **imprimante** dans la barre d’outils rapport, le contrôle Microsoft ActiveX est téléchargé sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7d51a-110">The first time a user clicks the **Printer** icon on the report toolbar, the Microsoft ActiveX control is downloaded to the computer.</span></span> <span data-ttu-id="7d51a-111">Une fois le contrôle téléchargé, la boîte de dialogue **Imprimer** s’affiche chaque fois que l’utilisateur clique sur l’icône de l' **imprimante** .</span><span class="sxs-lookup"><span data-stu-id="7d51a-111">After the control is downloaded, the **Print** dialog box displays whenever the user clicks the **Printer** icon.</span></span>  
  
 <span data-ttu-id="7d51a-112">En fonction des paramètres du navigateur, l'installation du contrôle peut être demandée à l'utilisateur, être bloquée ou s'effectuer de manière transparente en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="7d51a-112">Depending on browser settings, the user may be prompted to install the control, be prevented from installing the control, or have the control install transparently in the background.</span></span>  
  
 <span data-ttu-id="7d51a-113">Pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, les paramètres qui affectent le téléchargement et l’installation du contrôle ActiveX sont spécifiés via le nœud **contrôles ActiveX et plug-ins** de la page **paramètres de sécurité** de la zone de contenu Web.</span><span class="sxs-lookup"><span data-stu-id="7d51a-113">For [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, settings that affect ActiveX control download and installation are specified through the **ActiveX controls and plug-ins** node in the **Security Settings** page for the Web content zone.</span></span> <span data-ttu-id="7d51a-114">Les paramètres suivants déterminent si les utilisateurs peuvent télécharger et exécuter le contrôle d'impression, en fonction des spécifications de sécurité de la zone Web :</span><span class="sxs-lookup"><span data-stu-id="7d51a-114">The following settings determine whether users can download and run the print control, based on Web zone security preferences:</span></span>  
  
-   <span data-ttu-id="7d51a-115">Télécharger les contrôles ActiveX signés.</span><span class="sxs-lookup"><span data-stu-id="7d51a-115">Download signed ActiveX controls.</span></span>  
  
-   <span data-ttu-id="7d51a-116">Contrôles ActiveX reconnus sûrs pour l'écriture de scripts.</span><span class="sxs-lookup"><span data-stu-id="7d51a-116">Script ActiveX controls marked safe for scripting.</span></span>  
  
-   <span data-ttu-id="7d51a-117">Exécuter les contrôles ActiveX et les plug-ins.</span><span class="sxs-lookup"><span data-stu-id="7d51a-117">Run ActiveX controls and plug-ins.</span></span>  
  
 <span data-ttu-id="7d51a-118">Les utilisateurs qui souhaitent utiliser **RSClientPrint** pour effectuer une impression côté client doivent activer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7d51a-118">Users who want to use **RSClientPrint** to perform client-side printing must enable the following:</span></span>  
  
-   <span data-ttu-id="7d51a-119">**Téléchargez les contrôles ActiveX signés** et **le contrôle ActiveX de script marqués comme sécurisés** pour l’écriture de scripts à des fins d’installation.</span><span class="sxs-lookup"><span data-stu-id="7d51a-119">**Download signed ActiveX controls** and **Script ActiveX control marked safe for scripting** for installation purposes.</span></span>  
  
-   <span data-ttu-id="7d51a-120">**Exécuter les contrôles ActiveX et les plug-ins** pour les opérations d’impression en cours.</span><span class="sxs-lookup"><span data-stu-id="7d51a-120">**Run ActiveX controls and plug-ins** for ongoing print operations.</span></span>  
  
 <span data-ttu-id="7d51a-121">Le contrôle ActiveX **RSClientPrint** est signé, ce qui signifie qu’il contient un certificat numérique valide de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d51a-121">The **RSClientPrint** ActiveX control is signed, meaning it contains a valid digital certificate from [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="enabling-and-disabling-client-side-printing"></a><span data-ttu-id="7d51a-122">Activation et désactivation de l'impression côté client</span><span class="sxs-lookup"><span data-stu-id="7d51a-122">Enabling and Disabling Client-Side Printing</span></span>  
 <span data-ttu-id="7d51a-123">Les administrateurs du serveur de rapports ont la possibilité de désactiver la fonctionnalité d’impression en affectant à la propriété système du serveur de rapports **EnableClientPrinting** la valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="7d51a-123">Report server administrators have the option of disabling the print feature by setting the report server system property **EnableClientPrinting** to `false`.</span></span> <span data-ttu-id="7d51a-124">Cela entraîne la désactivation de l'impression côté client pour tous les rapports gérés par ce serveur.</span><span class="sxs-lookup"><span data-stu-id="7d51a-124">This will disable client-side printing for all reports managed by that server.</span></span> <span data-ttu-id="7d51a-125">Par défaut, **EnableClientPrinting** a la valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="7d51a-125">By default, **EnableClientPrinting** is set to `true`.</span></span> <span data-ttu-id="7d51a-126">Vous pouvez désactiver l'impression côté client de différentes façons :</span><span class="sxs-lookup"><span data-stu-id="7d51a-126">You can disable client-side printing in the following ways:</span></span>  
  
-   <span data-ttu-id="7d51a-127">Pour un **serveur de rapports en mode natif**:</span><span class="sxs-lookup"><span data-stu-id="7d51a-127">For a **Native mode report server**:</span></span>  
  
    1.  <span data-ttu-id="7d51a-128">Lancez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="7d51a-128">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    2.  <span data-ttu-id="7d51a-129">Connectez-vous à une instance de serveur de rapports dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d51a-129">Connect to a report server instance in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
    3.  <span data-ttu-id="7d51a-130">Cliquez avec le bouton droit sur le nœud du serveur de rapports et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-130">Right-click the report server node, and then click **Properties**.</span></span> <span data-ttu-id="7d51a-131">Si l'option **Propriétés** est désactivée, vérifiez que vous avez lancé [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="7d51a-131">If the **Properties** option is disabled, verify you started [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    4.  <span data-ttu-id="7d51a-132">Sélectionnez **activer le téléchargement pour le contrôle d’impression du client ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-132">Select **Enable download for the ActiveX client print control**.</span></span>  
  
    5.  <span data-ttu-id="7d51a-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-133">Click **OK**.</span></span>  
  
-   <span data-ttu-id="7d51a-134">Pour un **serveur de rapports en mode SharePoint**:</span><span class="sxs-lookup"><span data-stu-id="7d51a-134">For a **SharePoint mode report server**:</span></span>  
  
    1.  <span data-ttu-id="7d51a-135">Dans l'Administration centrale de SharePoint, cliquez sur **Gestion des applications**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-135">In SharePoint Central Administration, click **Application Management**.</span></span>  
  
    2.  <span data-ttu-id="7d51a-136">Cliquez sur **Gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-136">Click **Manage service applications**.</span></span>  
  
    3.  <span data-ttu-id="7d51a-137">Cliquez sur le nom de votre application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et cliquez sur **Gérer** dans le ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7d51a-137">Click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application, and then click **Manage** in the SharePoint ribbon.</span></span>  
  
    4.  <span data-ttu-id="7d51a-138">Cliquez sur **Paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-138">Click **System Settings**.</span></span>  
  
    5.  <span data-ttu-id="7d51a-139">Sélectionnez **Activer l'impression cliente**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-139">Select **Enable Client Printing**.</span></span> <span data-ttu-id="7d51a-140">L'option **Activer l'impression cliente** se trouve en bas de la page.</span><span class="sxs-lookup"><span data-stu-id="7d51a-140">The **Enable Client Printing** option is near the bottom of the page.</span></span>  
  
    6.  <span data-ttu-id="7d51a-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-141">Click **OK**.</span></span>  
  
-   <span data-ttu-id="7d51a-142">Écrire un script ou du code pour définir la propriété système du serveur de rapports **EnableClientPrinting** sur`false.`</span><span class="sxs-lookup"><span data-stu-id="7d51a-142">Write script or code to set the report server system property **EnableClientPrinting** to `false.`</span></span>  
  
 <span data-ttu-id="7d51a-143">L'exemple de script suivant illustre une approche possible en matière de désactivation de l'impression côté client.</span><span class="sxs-lookup"><span data-stu-id="7d51a-143">The following sample script illustrates one approach for disabling client-side printing.</span></span> <span data-ttu-id="7d51a-144">Compilez et exécutez le code [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] suivant afin d'affecter à la propriété **EnableClientPrinting** la valeur **False**.</span><span class="sxs-lookup"><span data-stu-id="7d51a-144">Compile and then run the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code to set the **EnableClientPrinting** property to **False**.</span></span> <span data-ttu-id="7d51a-145">Une fois le code exécuté, redémarrez les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="7d51a-145">After you run the code, restart IIS.</span></span>  
  
### <a name="sample-script"></a><span data-ttu-id="7d51a-146">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="7d51a-146">Sample Script</span></span>  
  
```  
Imports System  
Imports System.Web.Services.Protocols  
Class Sample  
   Public Shared Sub Main()  
Dim rs As New ReportingService()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
        Dim props(0) As [Property]  
        Dim setProp As New [Property]  
        setProp.Name = "EnableClientPrinting"  
        setProp.Value = "False"   
        props(0) = setProp  
        Try  
            rs.SetSystemProperties(props)  
        Catch ex As System.Web.Services.Protocols.SoapException  
            Console.Write(ex.Detail.InnerXml)  
        Catch e as Exception  
            Console.Write(e.Message)  
        End Try  
    End Sub 'Main  
End Class 'Sample  
```  
  
  
