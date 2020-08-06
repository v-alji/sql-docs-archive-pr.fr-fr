---
title: Modélisation tabulaire (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80027288-c203-4667-a3e1-40fa572b4975
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44f358f0f36e84ad903a0a4fcb0203291019e7aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603059"
---
# <a name="tabular-modeling-ssas-tabular"></a><span data-ttu-id="9631f-102">Modélisation tabulaire (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="9631f-102">Tabular Modeling (SSAS Tabular)</span></span>
  <span data-ttu-id="9631f-103">Les modèles tabulaires sont des bases de données en mémoire dans Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9631f-103">Tabular models are in-memory databases in Analysis Services.</span></span> <span data-ttu-id="9631f-104">À l'aide d'algorithmes de compression de pointe et du processeur de requêtes multithread, le moteur d'analyse en mémoire xVelocity (VertiPaq) permet un accès rapide aux objets de modèles tabulaires et aux données par les applications clientes de création de rapports telles que Microsoft Excel et Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9631f-104">Using state-of-the-art compression algorithms and multi-threaded query processor, the xVelocity in-memory analytics engine (VertiPaq) delivers fast access to tabular model objects and data by reporting client applications such as Microsoft Excel and Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
 <span data-ttu-id="9631f-105">Les modèles tabulaires prennent en charge l'accès aux données selon deux modes : mode mis en cache et mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="9631f-105">Tabular models support data access through two modes: Cached mode and DirectQuery mode.</span></span> <span data-ttu-id="9631f-106">En mode mis en cache, vous pouvez intégrer des données de plusieurs sources, notamment des bases de données relationnelles, des flux de données et des fichiers texte en deux dimensions.</span><span class="sxs-lookup"><span data-stu-id="9631f-106">In cached mode, you can integrate data from multiple sources including relational databases, data feeds, and flat text files.</span></span> <span data-ttu-id="9631f-107">En mode DirectQuery, vous pouvez ignorer le modèle en mémoire, ce qui permet aux applications clientes d'interroger des données directement au niveau de la source (SQL Server relationnel).</span><span class="sxs-lookup"><span data-stu-id="9631f-107">In DirectQuery mode, you can bypass the in-memory model, allowing client applications to query data directly at the (SQL Server relational) source.</span></span>  
  
 <span data-ttu-id="9631f-108">Les modèles tabulaires sont créés dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] à l'aide de nouveaux modèles de projet de modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="9631f-108">Tabular models are authored in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] using new tabular model project templates.</span></span> <span data-ttu-id="9631f-109">Vous pouvez importer des données depuis plusieurs sources, puis enrichir le modèle en ajoutant des relations, des colonnes calculées, des mesures, des indicateurs de performance clés et des hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="9631f-109">You can import data from multiple sources, and then enrich the model by adding relationships, calculated columns, measures, KPIs, and hierarchies.</span></span> <span data-ttu-id="9631f-110">Des modèles peuvent ensuite être déployés sur une instance d'Analysis Services à laquelle les applications clientes de création de rapports peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="9631f-110">Models can then be deployed to an instance of Analysis Services where client reporting applications can connect to them.</span></span> <span data-ttu-id="9631f-111">Les modèles déployés peuvent être gérés dans SQL Server Management Studio comme tous les modèles multidimensionnels.</span><span class="sxs-lookup"><span data-stu-id="9631f-111">Deployed models can be managed in SQL Server Management Studio just like multidimensional models.</span></span> <span data-ttu-id="9631f-112">Ils peuvent également être partitionnés pour un traitement optimisé et être sécurisés au niveau de la ligne à l'aide de la sécurité basée sur le rôle.</span><span class="sxs-lookup"><span data-stu-id="9631f-112">They can also be partitioned for optimized processing and secured to the row-level by using role based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9631f-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9631f-113">In This Section</span></span>  
 [<span data-ttu-id="9631f-114">Solutions de modèles tabulaires &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="9631f-114">Tabular Model Solutions &#40;SSAS Tabular&#41;</span></span>](../tabular-model-solutions-ssas-tabular.md)  
  
 [<span data-ttu-id="9631f-115">Bases de données model tabulaires #40;SSAS Tabulaire#41;</span><span class="sxs-lookup"><span data-stu-id="9631f-115">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-model-databases-ssas-tabular.md)  
  
 [<span data-ttu-id="9631f-116">Accès aux données de modèle tabulaire</span><span class="sxs-lookup"><span data-stu-id="9631f-116">Tabular Model Data Access</span></span>](tabular-model-data-access.md)  
  
  
