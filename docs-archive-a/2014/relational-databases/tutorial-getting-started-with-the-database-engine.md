---
title: 'Didacticiel : Mise en route du moteur de base de données | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorials [connecting]
- tutorials [Database Engine]
- unable to connect [SQL Server]
- failure to connect [SQL Server]
- connecting tutorial [SQL Server]
ms.assetid: 655e709b-346b-469c-bddc-a5a0238d07e0
author: rothja
ms.author: jroth
ms.openlocfilehash: aaa1fb21c026d064c2b14db73aadc2b82e9c15d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613865"
---
# <a name="tutorial-getting-started-with-the-database-engine"></a><span data-ttu-id="d3ff0-102">Didacticiel : mise en route du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="d3ff0-102">Tutorial: Getting Started with the Database Engine</span></span>
  <span data-ttu-id="d3ff0-103">Bienvenue dans le didacticiel de mise en route du [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3ff0-103">Welcome to the Getting Started with the [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorial.</span></span> <span data-ttu-id="d3ff0-104">Ce didacticiel est destiné aux nouveaux utilisateurs de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] disposant de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3ff0-104">This tutorial is intended for users who are new to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and who have installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="d3ff0-105">Ce didacticiel sommaire vous guide dans vos premiers pas avec le [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3ff0-105">This brief tutorial helps you get started using the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="d3ff0-106">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="d3ff0-106">What You Will Learn</span></span>  
 <span data-ttu-id="d3ff0-107">Ce didacticiel explique comment se connecter au [!INCLUDE[ssDE](../includes/ssde-md.md)] sur l'ordinateur local et depuis un autre ordinateur à l'aide de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ff0-107">This tutorial shows you how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] on both the local computer and from another computer.</span></span>  
  
 <span data-ttu-id="d3ff0-108">Ce didacticiel est divisé en deux leçons :</span><span class="sxs-lookup"><span data-stu-id="d3ff0-108">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="d3ff0-109">Leçon 1 : connexion au moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="d3ff0-109">Lesson 1: Connecting to the Database Engine</span></span>](lesson-1-connecting-to-the-database-engine.md)  
 <span data-ttu-id="d3ff0-110">Dans cette leçon, vous allez apprendre à vous connecter au [!INCLUDE[ssDE](../includes/ssde-md.md)] et à autoriser d’autres personnes à se connecter.</span><span class="sxs-lookup"><span data-stu-id="d3ff0-110">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] and enable additional people to connect.</span></span>  
  
 [<span data-ttu-id="d3ff0-111">Leçon 2 : Connexion depuis un autre ordinateur</span><span class="sxs-lookup"><span data-stu-id="d3ff0-111">Lesson 2: Connecting from Another Computer</span></span>](lesson-2-connecting-from-another-computer.md)  
 <span data-ttu-id="d3ff0-112">Dans cette leçon, vous allez apprendre à vous connecter au [!INCLUDE[ssDE](../includes/ssde-md.md)] à partir d’un deuxième ordinateur, notamment en activant des protocoles et en configurant des ports et des paramètres de pare-feu.</span><span class="sxs-lookup"><span data-stu-id="d3ff0-112">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] from a second computer, including enabling protocols, configuring ports, and configuring firewall settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ff0-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="d3ff0-113">Requirements</span></span>  
 <span data-ttu-id="d3ff0-114">Ce didacticiel n'exige aucune connaissance préalable.</span><span class="sxs-lookup"><span data-stu-id="d3ff0-114">This tutorial has no knowledge prerequisites.</span></span>  
  
 <span data-ttu-id="d3ff0-115">Les éléments suivants doivent cependant être installés sur votre système :</span><span class="sxs-lookup"><span data-stu-id="d3ff0-115">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="d3ff0-116">.</span><span class="sxs-lookup"><span data-stu-id="d3ff0-116">.</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] <span data-ttu-id="d3ff0-117">peut être installé en exécutant le programme d'installation de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou en le téléchargeant et en l'installant à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?LinkId=144346).</span><span class="sxs-lookup"><span data-stu-id="d3ff0-117">can be installed by running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup or by downloading and installing from [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=144346).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ff0-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3ff0-118">See Also</span></span>  
 [<span data-ttu-id="d3ff0-119">Didacticiel : SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d3ff0-119">Tutorial: SQL Server Management Studio</span></span>](../ssms/tutorials/tutorial-sql-server-management-studio.md)  
  
  
