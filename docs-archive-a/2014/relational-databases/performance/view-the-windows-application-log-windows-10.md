---
title: Afficher le journal des applications Windows (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- application logs [SQL Server]
- logs [SQL Server], application
- monitoring Windows NT application log [SQL Server]
- Windows NT application logs [SQL Server]
- displaying logs
- monitoring [SQL Server], events
- logs [SQL Server], viewing
ms.assetid: 168a6c6e-12df-46a9-9904-55d63ca8fe14
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1255e95833d9fc56abd1700f5acb0d2f49ebf77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699510"
---
# <a name="view-the-windows-application-log-windows"></a><span data-ttu-id="4324e-102">Afficher le journal des applications Windows (Windows)</span><span class="sxs-lookup"><span data-stu-id="4324e-102">View the Windows Application Log (Windows)</span></span>
  <span data-ttu-id="4324e-103">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré pour vous permettre d'utiliser le journal des applications Windows, chaque session [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y enregistre des nouveaux événements.</span><span class="sxs-lookup"><span data-stu-id="4324e-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="4324e-104">Contrairement au journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , un nouveau journal des applications n'est pas créé chaque fois que vous démarrez une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4324e-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-the-windows-application-log"></a><span data-ttu-id="4324e-105">Pour consulter le journal des applications Windows</span><span class="sxs-lookup"><span data-stu-id="4324e-105">To view the Windows application log</span></span>  
  
1.  <span data-ttu-id="4324e-106">Dans le menu **Démarrer** , pointez successivement sur **Tous les programmes**et **Outils d'administration**, puis cliquez sur **Observateur d’événements**.</span><span class="sxs-lookup"><span data-stu-id="4324e-106">On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="4324e-107">Dans l'Observateur d'événements, cliquez sur **Application**.</span><span class="sxs-lookup"><span data-stu-id="4324e-107">In Event Viewer, click **Application**.</span></span>  
  
3.  <span data-ttu-id="4324e-108">Les événements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont identifiés par l’entrée **MSSQLSERVER** (les instances nommées sont identifiées par **MSSQL$** _<nom_instance>_ ) dans la colonne **Source**.</span><span class="sxs-lookup"><span data-stu-id="4324e-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events are identified by the entry **MSSQLSERVER** (named instances are identified with **MSSQL$**_<instance_name>_) in the **Source** column.</span></span> <span data-ttu-id="4324e-109">Les événements de SQL Server Agent sont identifiés par l’entrée SQLSERVERAGENT (pour les instances nommées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les événements de l’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont identifiés par **SQLAgent$** \<*instance_name*>).</span><span class="sxs-lookup"><span data-stu-id="4324e-109">SQL Server Agent events are identified by the entry SQLSERVERAGENT (for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events are identified with **SQLAgent$**\<*instance_name*>).</span></span> <span data-ttu-id="4324e-110">Les événements du service Microsoft Search sont identifiés par l'entrée **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="4324e-110">Microsoft Search service events are identified by the entry **Microsoft Search**.</span></span>  
  
4.  <span data-ttu-id="4324e-111">Pour afficher le journal d’un autre ordinateur, cliquez avec le bouton droit sur **Observateur d’événements**, cliquez sur **Se connecter à un autre ordinateur** , et renseignez la boîte de dialogue **Sélectionner un ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="4324e-111">To view the log of a different computer, right-click **Event Viewer**, click **Connect to another computer,** and complete the **Select Computer**dialog box.</span></span>  
  
5.  <span data-ttu-id="4324e-112">Pour afficher uniquement les événements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , dans le menu **Affichage** , cliquez sur **Filtrer**et dans la liste **Source de l'événement** , sélectionnez **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="4324e-112">Optionally, to display only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, on the **View** menu click **Filter**, and in the **Event source** list, select **MSSQLSERVER**.</span></span> <span data-ttu-id="4324e-113">Pour afficher uniquement les événements de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sélectionnez **SQLSERVERAGENT** dans la liste **Source de l'événement** .</span><span class="sxs-lookup"><span data-stu-id="4324e-113">To view only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events, instead select **SQLSERVERAGENT** in the **Event source** list.</span></span>  
  
6.  <span data-ttu-id="4324e-114">Pour obtenir plus de détails sur un événement particulier, double-cliquez sur cet événement.</span><span class="sxs-lookup"><span data-stu-id="4324e-114">To view more information about an event, double-click the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4324e-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4324e-115">See Also</span></span>  
 [<span data-ttu-id="4324e-116">Afficher le journal des erreurs SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4324e-116">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
