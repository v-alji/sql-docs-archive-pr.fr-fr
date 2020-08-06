---
title: Importer une stratégie de gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, import policy
ms.assetid: 850b7ef9-d2b7-4754-bf04-7cb419ffb776
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d83ed589e147c61b1692447aacb17535f18a5c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601430"
---
# <a name="import-a-policy-based-management-policy"></a><span data-ttu-id="79e98-102">Importer une stratégie de gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="79e98-102">Import a Policy-Based Management Policy</span></span>
  <span data-ttu-id="79e98-103">Cette rubrique explique comment importer une instance de stratégie de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79e98-103">This topic describes how to import a Policy-Based Management policy instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="79e98-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="79e98-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="79e98-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="79e98-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="79e98-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="79e98-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="79e98-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="79e98-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="79e98-108">**Pour importer une instance de stratégie à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="79e98-108">**To import a policy instance, using:**</span></span>  
  
     [<span data-ttu-id="79e98-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="79e98-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="79e98-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="79e98-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="79e98-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="79e98-111">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="79e98-112">est fourni avec des stratégies qui peuvent être utilisées pour contrôler une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79e98-112">ships with policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="79e98-113">Par défaut, ces stratégies ne sont pas installées sur le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], mais elles peuvent être importées à partir de l'emplacement par défaut C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="79e98-113">By default, these policies are not installed on the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], but they can be imported from the default location of C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="79e98-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="79e98-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="79e98-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="79e98-115">Permissions</span></span>  
 <span data-ttu-id="79e98-116">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="79e98-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="79e98-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="79e98-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-import-a-policy-instance"></a><span data-ttu-id="79e98-118">Pour importer une instance de stratégie</span><span class="sxs-lookup"><span data-stu-id="79e98-118">To import a policy instance</span></span>  
  
1.  <span data-ttu-id="79e98-119">Dans **l’Explorateur d’objets**, cliquez sur le signe plus (+) pour développer le serveur où l’instance de stratégie importée résidera.</span><span class="sxs-lookup"><span data-stu-id="79e98-119">In **Object Explorer**, click the plus sign to expand the server where the newly-imported policy instance will reside.</span></span>  
  
2.  <span data-ttu-id="79e98-120">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="79e98-120">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="79e98-121">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="79e98-121">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="79e98-122">Cliquez avec le bouton droit sur le dossier **Stratégies** et sélectionnez **Importer une stratégie**.</span><span class="sxs-lookup"><span data-stu-id="79e98-122">Right-click the **Policies** folder and select **Import Policy**.</span></span>  
  
5.  <span data-ttu-id="79e98-123">Dans la boîte de dialogue **Importer** , tapez le nom et le chemin du fichier ou utilisez le bouton Parcourir ( **...** ) pour rechercher et sélectionner le fichier XML qui contient la stratégie.</span><span class="sxs-lookup"><span data-stu-id="79e98-123">In the **Import** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the XML file that contains the policy, and then select the file.</span></span> <span data-ttu-id="79e98-124">Pour plus d'informations sur les options disponibles dans la boîte de dialogue **Importer** , consultez [Import Policies Dialog Box](import-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="79e98-124">For more information on the available options in the **Import** dialog box, see [Import Policies Dialog Box](import-policies-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="79e98-125">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="79e98-125">When finished, click **OK**.</span></span>  
  
  
