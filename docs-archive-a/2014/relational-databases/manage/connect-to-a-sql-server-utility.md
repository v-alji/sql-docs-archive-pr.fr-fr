---
title: Se connecter à un utilitaire SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: b9b90b8d-241f-4b74-ac14-de7b10ea1821
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8e59a28e083fc302faebbcba932c18a04e73a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602136"
---
# <a name="connect-to-a-sql-server-utility"></a><span data-ttu-id="dbb15-102">Se connecter à un utilitaire SQL Server</span><span class="sxs-lookup"><span data-stu-id="dbb15-102">Connect to a SQL Server Utility</span></span>
  <span data-ttu-id="dbb15-103">Avant de vous connecter à un utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez créer un point de contrôle de l’utilitaire (UCP).</span><span class="sxs-lookup"><span data-stu-id="dbb15-103">Before you can connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, you must create a utility control point (UCP).</span></span> <span data-ttu-id="dbb15-104">Pour plus d’informations, consultez [Fonctionnalités et tâches de l’utilitaire SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="dbb15-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>

 <span data-ttu-id="dbb15-105">Pour afficher et gérer l’intégrité des ressources de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilisez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) pour vous connecter à un utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dbb15-105">To view and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource health, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>

 <span data-ttu-id="dbb15-106">Pour vous connecter à un utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] via SSMS :</span><span class="sxs-lookup"><span data-stu-id="dbb15-106">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility through SSMS:</span></span>

1.  <span data-ttu-id="dbb15-107">Lancez SSMS.</span><span class="sxs-lookup"><span data-stu-id="dbb15-107">Launch SSMS.</span></span>

2.  <span data-ttu-id="dbb15-108">Dans SSMS, connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbb15-108">In SSMS, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

3.  <span data-ttu-id="dbb15-109">Cliquez sur **Affichage** , puis **Explorateur de l’utilitaire**.</span><span class="sxs-lookup"><span data-stu-id="dbb15-109">Click **View** and then **Utility Explorer**.</span></span>

4.  <span data-ttu-id="dbb15-110">Dans le volet Navigation de l’Explorateur de l’utilitaire, cliquez sur ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Se connecter à l’utilitaire**.</span><span class="sxs-lookup"><span data-stu-id="dbb15-110">In the Utility Explorer navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span>

5.  <span data-ttu-id="dbb15-111">Dans la boîte de dialogue **Se connecter au serveur** , spécifiez le nom de l’instance de l’UCP, puis cliquez **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="dbb15-111">In the **Connect to Server** dialog box, specify the UCP instance name, then click **Connect**.</span></span>

6.  <span data-ttu-id="dbb15-112">Affichez le volet Navigation de l’Explorateur de l’utilitaire pour consulter une arborescence des ressources de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans l’UCP.</span><span class="sxs-lookup"><span data-stu-id="dbb15-112">View the Utility Explorer Navigation Pane to see a tree view of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources in the UCP.</span></span>

 <span data-ttu-id="dbb15-113">La création d’un UCP vous connecte également à l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dbb15-113">Creating a new UCP also connects you to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="dbb15-114">Pour plus d’informations, consultez [Créer un point de contrôle de l’utilitaire SQL Server &#40;utilitaire SQL Server&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md)</span><span class="sxs-lookup"><span data-stu-id="dbb15-114">For more information, see [Create a SQL Server Utility Control Point &#40;SQL Server Utility&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dbb15-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbb15-115">See Also</span></span>
 <span data-ttu-id="dbb15-116">[Utilitaire SQL Server affichage des fonctionnalités et des tâches Resource Health les résultats de](sql-server-utility-features-and-tasks.md) la [stratégie &#40;utilitaire SQL Server&#41;](view-resource-health-policy-results-sql-server-utility.md)</span><span class="sxs-lookup"><span data-stu-id="dbb15-116">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) [View Resource Health Policy Results &#40;SQL Server Utility&#41;](view-resource-health-policy-results-sql-server-utility.md)</span></span>


