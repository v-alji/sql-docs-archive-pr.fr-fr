---
title: Copier un état de facette de gestion basée sur des stratégies dans un fichier XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, copy facet state to XML file
ms.assetid: 7d604ab1-6dd6-4f8e-a79c-eba99ab106fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7be2332d9a2507a079d85a3424bda3a387609ca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699467"
---
# <a name="copy-a-policy-based-management-facet-state-to-an-xml-file"></a><span data-ttu-id="07fc8-102">Copier un état de facette de gestion basée sur des stratégies dans un fichier XML</span><span class="sxs-lookup"><span data-stu-id="07fc8-102">Copy a Policy-Based Management Facet State to an XML File</span></span>
  <span data-ttu-id="07fc8-103">Cette rubrique explique comment copier l'état d'une facette de gestion basée sur des stratégies dans un fichier XML dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07fc8-103">This topic describes how to how to copy the state of a Policy-Based Management facet to an XML file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="07fc8-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="07fc8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="07fc8-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="07fc8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="07fc8-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07fc8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="07fc8-107">**Pour copier un état de facette dans un fichier XML à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="07fc8-107">**To copy a facet state to an XML file, using:**</span></span>  
  
     [<span data-ttu-id="07fc8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="07fc8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="07fc8-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="07fc8-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="07fc8-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07fc8-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="07fc8-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="07fc8-111">Permissions</span></span>  
 <span data-ttu-id="07fc8-112">Les procédures de cette rubrique nécessite l’appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="07fc8-112">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="07fc8-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="07fc8-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-a-facet-state-to-an-xml-file"></a><span data-ttu-id="07fc8-114">Pour copier un état de facette dans un fichier XML</span><span class="sxs-lookup"><span data-stu-id="07fc8-114">To copy a facet state to an XML file</span></span>  
  
1.  <span data-ttu-id="07fc8-115">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un objet d’instance, une base de données ou un objet de base de données, puis cliquez sur **Facettes**.</span><span class="sxs-lookup"><span data-stu-id="07fc8-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="07fc8-116">Dans la boîte de dialogue **Afficher les facettes -**_nom_objet_, cliquez sur **Exporter l’état actuel en tant que stratégie**.</span><span class="sxs-lookup"><span data-stu-id="07fc8-116">In the **View Facets -**_object_name_ dialog box, click **Export Current State as Policy**.</span></span>  
  
3.  <span data-ttu-id="07fc8-117">Dans la boîte de dialogue **Exporter en tant que stratégie** , tapez le nom et le chemin du fichier ou utilisez le bouton Parcourir (**...**) pour rechercher le fichier, puis tapez le nom du fichier XML.</span><span class="sxs-lookup"><span data-stu-id="07fc8-117">In the **Export as Policy** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the file, and then type the name of the XML file.</span></span> <span data-ttu-id="07fc8-118">Pour plus d'informations sur les options disponibles dans cette boîte de dialogue, consultez [Export As Policy Dialog Box](export-as-policy-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="07fc8-118">For more information on the available options in this dialog box, see [Export As Policy Dialog Box](export-as-policy-dialog-box.md)</span></span>  
  
4.  <span data-ttu-id="07fc8-119">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="07fc8-119">When finished, click **OK**.</span></span>  
  
  
