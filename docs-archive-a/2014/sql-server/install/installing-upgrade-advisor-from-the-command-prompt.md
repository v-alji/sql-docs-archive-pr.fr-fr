---
title: Installation du conseiller de mise à niveau à partir de l’invite de commandes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- command prompt [Upgrade Advisor]
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: a6841cc2-ca13-4b1c-9343-9e4d54312c3a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b0c5193f0b235b6d37170992d9d7ca9568b1f675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697404"
---
# <a name="installing-upgrade-advisor-from-the-command-prompt"></a><span data-ttu-id="cc08c-102">Installation du Conseiller de mise à niveau à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="cc08c-102">Installing Upgrade Advisor from the Command Prompt</span></span>
  <span data-ttu-id="cc08c-103">Vous pouvez installer le Conseiller de mise à niveau à l'aide de l'Assistant Installation ou à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="cc08c-103">You can install Upgrade Advisor either by using the Setup Wizard or from the command prompt.</span></span> <span data-ttu-id="cc08c-104">L'invite de commandes vous permet d'effectuer des installations automatisées et sans assistance.</span><span class="sxs-lookup"><span data-stu-id="cc08c-104">By using the command prompt you can perform unattended and automated installations.</span></span>  
  
## <a name="installation-syntax"></a><span data-ttu-id="cc08c-105">Syntaxe d'installation</span><span class="sxs-lookup"><span data-stu-id="cc08c-105">Installation Syntax</span></span>  
 <span data-ttu-id="cc08c-106">La syntaxe de base pour installer le Conseiller de mise à niveau à partir de l'invite de commandes est la suivante :</span><span class="sxs-lookup"><span data-stu-id="cc08c-106">The basic syntax for installing Upgrade Advisor from the command prompt is as follows:</span></span>  
  
 `SQLUA.msi [options]`  
  
 <span data-ttu-id="cc08c-107">Le tableau suivant affiche les options les plus courantes.</span><span class="sxs-lookup"><span data-stu-id="cc08c-107">The following table shows the most common options.</span></span>  
  
|<span data-ttu-id="cc08c-108">Argument</span><span class="sxs-lookup"><span data-stu-id="cc08c-108">Argument</span></span>|<span data-ttu-id="cc08c-109">Description</span><span class="sxs-lookup"><span data-stu-id="cc08c-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="cc08c-110">/q [n&#124;b&#124;r&#124;f]</span><span class="sxs-lookup"><span data-stu-id="cc08c-110">/q[n&#124;b&#124;r&#124;f]</span></span>|<span data-ttu-id="cc08c-111">Définit le niveau de l'interface utilisateur (UI) :</span><span class="sxs-lookup"><span data-stu-id="cc08c-111">Sets user interface (UI) level:</span></span><br /><br /> <span data-ttu-id="cc08c-112">n = aucune interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="cc08c-112">n = no UI</span></span><br /><br /> <span data-ttu-id="cc08c-113">b = interface utilisateur de base (progression uniquement, aucune invite)</span><span class="sxs-lookup"><span data-stu-id="cc08c-113">b = basic UI (progress only, no prompts)</span></span><br /><br /> <span data-ttu-id="cc08c-114">r = interface utilisateur réduite (boîte de dialogue à la fin de l'installation)</span><span class="sxs-lookup"><span data-stu-id="cc08c-114">r = reduced UI (dialog box at the end of installation)</span></span><br /><br /> <span data-ttu-id="cc08c-115">f = interface utilisateur complète</span><span class="sxs-lookup"><span data-stu-id="cc08c-115">f = full UI</span></span>|  
|<span data-ttu-id="cc08c-116">/L</span><span class="sxs-lookup"><span data-stu-id="cc08c-116">/L</span></span>|<span data-ttu-id="cc08c-117">Spécifie les options du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="cc08c-117">Specifies log file options.</span></span> <span data-ttu-id="cc08c-118">Pour consigner tous les messages dans *log_file_name*, utilisez **-L \* v**_log_file_name_.</span><span class="sxs-lookup"><span data-stu-id="cc08c-118">To log all messages to *log_file_name*, use **-L\*v**_log_file_name_.</span></span> <span data-ttu-id="cc08c-119">Pour consigner les messages d’erreur uniquement, utilisez `-Le` *log_file_name*.</span><span class="sxs-lookup"><span data-stu-id="cc08c-119">To log error messages only, use `-Le`*log_file_name*.</span></span>|  
|<span data-ttu-id="cc08c-120">ADDLOCAL = ALL&#124; REMOVE = ALL&#124;REINSTALL = ALL</span><span class="sxs-lookup"><span data-stu-id="cc08c-120">ADDLOCAL=ALL&#124; REMOVE=ALL&#124;REINSTALL=ALL</span></span>|<span data-ttu-id="cc08c-121">Spécifie que le Conseiller de mise à niveau doit être installé (ADDLOCAL), supprimé (REMOVE) ou réinstallé (REINSTALL).</span><span class="sxs-lookup"><span data-stu-id="cc08c-121">Specifies to install (ADDLOCAL), remove (REMOVE), or reinstall (REINSTALL) Upgrade Advisor.</span></span>|  
|<span data-ttu-id="cc08c-122">UAINSTALLDIR=path</span><span class="sxs-lookup"><span data-stu-id="cc08c-122">UAINSTALLDIR=path</span></span>|<span data-ttu-id="cc08c-123">Installe le Conseiller de mise à niveau à l'emplacement spécifié par le chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="cc08c-123">Installs Upgrade Advisor to the location specified by path.</span></span>|  
  
## <a name="installation-examples"></a><span data-ttu-id="cc08c-124">Exemples d'installation</span><span class="sxs-lookup"><span data-stu-id="cc08c-124">Installation Examples</span></span>  
 <span data-ttu-id="cc08c-125">L'exemple suivant indique comment installer le Conseiller de mise à niveau à l'aide de l'invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="cc08c-125">The following example shows how to install Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="cc08c-126">Vous pouvez également utiliser le programme Msiexec lorsque vous exécutez cette commande :</span><span class="sxs-lookup"><span data-stu-id="cc08c-126">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="cc08c-127">Cela peut s'avérer utile si vous devez utiliser des options d'installation supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="cc08c-127">This can be helpful if you have to use additional installation options.</span></span>  
  
## <a name="removal-examples"></a><span data-ttu-id="cc08c-128">Exemples de suppression</span><span class="sxs-lookup"><span data-stu-id="cc08c-128">Removal Examples</span></span>  
 <span data-ttu-id="cc08c-129">L'exemple suivant indique comment supprimer le Conseiller de mise à niveau à l'aide de l'invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="cc08c-129">The following example shows how to remove Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn REMOVE=ALL  
```  
  
 <span data-ttu-id="cc08c-130">Vous pouvez également utiliser le programme Msiexec lorsque vous exécutez cette commande :</span><span class="sxs-lookup"><span data-stu-id="cc08c-130">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn REMOVE=ALL  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc08c-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc08c-131">See Also</span></span>  
 <span data-ttu-id="cc08c-132">[Installation du conseiller de mise à niveau](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="cc08c-132">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="cc08c-133">Configuration requise par le Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cc08c-133">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
