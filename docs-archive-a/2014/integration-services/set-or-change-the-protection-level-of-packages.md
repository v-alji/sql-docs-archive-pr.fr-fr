---
title: Définir ou modifier le niveau de protection des packages | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- passwords [Integration Services]
- packages [Integration Services],security
- security [Integration Services],protection levels
- protection level for packages [Integration Services]
ms.assetid: 904a5580-82ba-4a26-b0c5-d1c989975f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da8e63028498097b4321e4ef1383fbc8aa5845b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708487"
---
# <a name="set-or-change-the-protection-level-of-packages"></a><span data-ttu-id="2d976-102">Définir ou modifier le niveau de protection des packages</span><span class="sxs-lookup"><span data-stu-id="2d976-102">Set or Change the Protection Level of Packages</span></span>
  <span data-ttu-id="2d976-103">Pour contrôler l'accès au contenu des packages et aux valeurs sensibles qu'ils contiennent, telles que les mots de passe, définissez la valeur de la propriété `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="2d976-103">To control access to the contents of packages and to the sensitive values that they contain, such as passwords, set the value of the `ProtectionLevel` property.</span></span> <span data-ttu-id="2d976-104">Les packages contenus dans un projet doivent avoir le même niveau de protection que le projet pour permettre sa génération.</span><span class="sxs-lookup"><span data-stu-id="2d976-104">The packages contained in a project need to have the same protection level as the project, to build the project.</span></span> <span data-ttu-id="2d976-105">Si vous modifiez le paramètre de propriété `ProtectionLevel` du projet, vous devez mettre à jour manuellement le paramètre de propriété des packages.</span><span class="sxs-lookup"><span data-stu-id="2d976-105">If you change the `ProtectionLevel` property setting on the project, you need to manually update the property setting for the packages.</span></span>  
  
 <span data-ttu-id="2d976-106">Pour plus d’informations sur la façon de déterminer les `ProtectionLevel` paramètres appropriés pour vos packages à différentes étapes du cycle de vie d’un package, consultez [Access Control pour obtenir des données sensibles dans des packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="2d976-106">For information about how to determine the `ProtectionLevel` settings that are appropriate for your packages at different stages in the package life cycle, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span> <span data-ttu-id="2d976-107">Pour obtenir une vue d’ensemble des fonctionnalités de sécurité dans [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], consultez [Vue d’ensemble de la sécurité &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="2d976-107">For an overview of security features in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], see [Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span></span>  
  
 <span data-ttu-id="2d976-108">Les procédures dans cette rubrique décrivent comment utiliser [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ou l'utilitaire en ligne de commande dtutil pour modifier la propriété `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="2d976-108">The procedures in this topic describe how to use either [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or the dtutil command prompt utility to change the `ProtectionLevel` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d976-109">En plus des procédures dans cette rubrique, vous pouvez en général définir ou modifier la propriété `ProtectionLevel` d'un package lorsque vous importez ou exportez le package.</span><span class="sxs-lookup"><span data-stu-id="2d976-109">In addition to the procedures in this topic, you can typically set or change the `ProtectionLevel` property of a package when you import or export the package.</span></span> <span data-ttu-id="2d976-110">Vous pouvez également modifier la propriété `ProtectionLevel` d'un package lorsque vous utilisez l'Assistant Importation et exportation [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour enregistrer un package.</span><span class="sxs-lookup"><span data-stu-id="2d976-110">You can also change the `ProtectionLevel` property of a package when you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to save a package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-a-package-in-sql-server-data-tools"></a><span data-ttu-id="2d976-111">Pour définir ou modifier le niveau de protection d'un package dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="2d976-111">To set or change the protection level of a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="2d976-112">Passez en revue les valeurs disponibles pour la `ProtectionLevel` propriété dans la rubrique [définition du niveau de protection des packages](security/access-control-for-sensitive-data-in-packages.md)et déterminez la valeur appropriée pour votre package.</span><span class="sxs-lookup"><span data-stu-id="2d976-112">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="2d976-113">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient le package.</span><span class="sxs-lookup"><span data-stu-id="2d976-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package.</span></span>  
  
3.  <span data-ttu-id="2d976-114">Ouvrez le package dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d976-114">Open the package in the [!INCLUDE[ssIS](../includes/ssis-md.md)] designer.</span></span>  
  
4.  <span data-ttu-id="2d976-115">Si la fenêtre Propriétés n'affiche pas les propriétés du package, cliquez sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="2d976-115">If the Properties window does not show the properties of the package, click the design surface.</span></span>  
  
5.  <span data-ttu-id="2d976-116">Dans le Fenêtre Propriétés, dans le groupe **sécurité** , sélectionnez la valeur appropriée pour la `ProtectionLevel` propriété.</span><span class="sxs-lookup"><span data-stu-id="2d976-116">In the Properties window, in the **Security** group, select the appropriate value for the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="2d976-117">Si vous sélectionnez un niveau de protection qui requiert un mot de passe, entrez le mot de passe comme valeur de la propriété **PackagePassword** .</span><span class="sxs-lookup"><span data-stu-id="2d976-117">If you select a protection level that requires a password, enter the password as the value of the **PackagePassword** property.</span></span>  
  
6.  <span data-ttu-id="2d976-118">Dans le menu **Fichier** , sélectionnez **Enregistrer les éléments sélectionnés** pour enregistrer le package modifié.</span><span class="sxs-lookup"><span data-stu-id="2d976-118">On the **File** menu, select **Save Selected Items** to save the modified package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-packages-at-the-command-prompt"></a><span data-ttu-id="2d976-119">Pour définir ou modifier le niveau de protection de package à l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="2d976-119">To set or change the protection level of packages at the command prompt</span></span>  
  
1.  <span data-ttu-id="2d976-120">Passez en revue les valeurs disponibles pour la `ProtectionLevel` propriété dans la rubrique [définition du niveau de protection des packages](security/access-control-for-sensitive-data-in-packages.md)et déterminez la valeur appropriée pour votre package.</span><span class="sxs-lookup"><span data-stu-id="2d976-120">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="2d976-121">Passez en revue les mappages de l' `Encrypt` option dans la rubrique [Utilitaire dtutil](dtutil-utility.md)et déterminez l’entier approprié à utiliser comme valeur de la `ProtectionLevel` propriété sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2d976-121">Review the mappings for the `Encrypt` option in the topic, [dtutil Utility](dtutil-utility.md), and determine the appropriate integer to use as the value of the selected `ProtectionLevel` property.</span></span>  
  
3.  <span data-ttu-id="2d976-122">Ouvrez une fenêtre d’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="2d976-122">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="2d976-123">À l'invite de commandes, naviguez jusqu'au dossier qui contient le ou les packages pour lesquels vous souhaitez définir la propriété `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="2d976-123">At the command prompt, navigate to the folder that contains the package or packages for which you want to set the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="2d976-124">Les exemples de syntaxe affichés à l'étape suivante supposent que ce dossier est le dossier actif.</span><span class="sxs-lookup"><span data-stu-id="2d976-124">The syntax examples shown in the following step assume that this folder is the current folder.</span></span>  
  
5.  <span data-ttu-id="2d976-125">Définissez ou modifiez le niveau de protection des packages en utilisant une commande semblable à celle des exemples suivants :</span><span class="sxs-lookup"><span data-stu-id="2d976-125">Set or change the protection level of the package or packages by using a command similar to the one of the following examples:</span></span>  
  
    -   <span data-ttu-id="2d976-126">La commande suivante définit la propriété `ProtectionLevel` d'un package dans le système de fichiers au niveau 2, « Chiffrer les données sensibles avec un mot de passe », avec le mot de passe « strongpassword » :</span><span class="sxs-lookup"><span data-stu-id="2d976-126">The following command sets the `ProtectionLevel` property of an individual package in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `dtutil.exe /file "C:\Package.dtsx" /encrypt file;"C:\Package.dtsx";2;strongpassword`  
  
    -   <span data-ttu-id="2d976-127">La commande suivante définit la propriété `ProtectionLevel` de tous les packages dans un dossier spécifique dans le système de fichiers au niveau 2, « Chiffrer les données sensibles avec un mot de passe », avec le mot de passe « strongpassword » :</span><span class="sxs-lookup"><span data-stu-id="2d976-127">The following command sets the `ProtectionLevel` property of all packages in a particular folder in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `for %f in (*.dtsx) do dtutil.exe /file %f /encrypt file;%f;2;strongpassword`  
  
         <span data-ttu-id="2d976-128">Si vous utilisez une commande semblable dans un fichier de commandes, entrez l'espace réservé de fichier, « % f », comme « %% f » dans le fichier de commandes.</span><span class="sxs-lookup"><span data-stu-id="2d976-128">If you use a similar command in a batch file, enter the file placeholder, "%f", as "%%f" in the batch file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d976-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d976-129">See Also</span></span>  
 [<span data-ttu-id="2d976-130">Utilitaire dtutil</span><span class="sxs-lookup"><span data-stu-id="2d976-130">dtutil Utility</span></span>](dtutil-utility.md)  
  
  
