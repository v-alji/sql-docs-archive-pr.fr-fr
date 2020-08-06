---
title: Masquer les objets système dans l’Explorateur d’objets | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- hiding system objects
- system objects [SQL Server]
- objects [SQL Server], hiding
- Object Explorer, hiding objects
ms.assetid: c01d8804-838c-4f75-b78c-80e41e4fffdc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e039446191154144dd6660fa6e8d3b4b65d1013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599759"
---
# <a name="hide-system-objects-in-object-explorer"></a><span data-ttu-id="8dc4a-102">Masquer les objets système dans l’Explorateur d’objets</span><span class="sxs-lookup"><span data-stu-id="8dc4a-102">Hide System Objects in Object Explorer</span></span>
  <span data-ttu-id="8dc4a-103">Cette rubrique explique comment masquer les objets système dans l'Explorateur d'objets dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dc4a-103">This topic describes how to hide system objects in Object Explorer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8dc4a-104">Le nœud **Bases de données** de l’Explorateur d’objets contient des objets système tels que les bases de données système.</span><span class="sxs-lookup"><span data-stu-id="8dc4a-104">The **Databases** node of Object Explorer contains system objects such as the system databases.</span></span> <span data-ttu-id="8dc4a-105">Utilisez les pages **Outils**/**Options** pour masquer les objets système.</span><span class="sxs-lookup"><span data-stu-id="8dc4a-105">Use the **Tools**/**Options** pages to hide the system objects.</span></span> <span data-ttu-id="8dc4a-106">Certains objets système, tels que les fonctions système et les types de données système, ne sont pas affectés par ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="8dc4a-106">Some system objects, such as system functions and system data types, are not affected by this setting.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8dc4a-107">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8dc4a-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-hide-system-objects-in-object-explorer"></a><span data-ttu-id="8dc4a-108">Pour masquer les objets système dans l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="8dc4a-108">To hide system objects in Object Explorer</span></span>  
  
1.  <span data-ttu-id="8dc4a-109">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="8dc4a-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="8dc4a-110">Dans la page **Environnement/Démarrage** , sélectionnez **Masquer les objets système dans l’Explorateur d’objets**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8dc4a-110">On the **Environment/Startup** page, select **Hide system objects in Object Explorer**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8dc4a-111">Dans la boîte de dialogue **SQL Server Management Studio** , cliquez sur **OK** pour que SQL Server Management Studio redémarre et que la modification prenne effet.</span><span class="sxs-lookup"><span data-stu-id="8dc4a-111">In the **SQL Server Management Studio** dialog box, click **OK** to acknowledge that SQL Server Management Studio must be restarted for this change to take effect.</span></span>  
  
4.  <span data-ttu-id="8dc4a-112">Fermez et rouvrez SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="8dc4a-112">Close and reopen SQL Server Management Studio.</span></span>  
  
  
