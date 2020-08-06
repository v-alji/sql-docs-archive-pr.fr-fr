---
title: Se connecter à un référentiel MDS (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 8f427312-4c09-4c8b-b9f9-8b235557a74b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c1db0594f07da7ff8a78642e4b2de0eb9e507164
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698381"
---
# <a name="connect-to-an-mds-repository-mds-add-in-for-excel"></a><span data-ttu-id="a0252-102">Se connecter à un référentiel MDS (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="a0252-102">Connect to an MDS Repository (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="a0252-103">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], vous devez vous connecter à un référentiel MDS avant de pouvoir charger ou publier des données.</span><span class="sxs-lookup"><span data-stu-id="a0252-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must connect to an MDS repository before you can load or publish data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a0252-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a0252-104">Prerequisites</span></span>  
 <span data-ttu-id="a0252-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="a0252-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a0252-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="a0252-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-connect-to-an-mds-repository"></a><span data-ttu-id="a0252-107">Pour vous connecter à un référentiel MDS</span><span class="sxs-lookup"><span data-stu-id="a0252-107">To connect to an MDS repository</span></span>  
  
1.  <span data-ttu-id="a0252-108">Dans le Complément MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], sous l’onglet **Données de référence** , dans le groupe **Se connecter et charger** , cliquez sur la flèche du bas sous le bouton **Se connecter** et cliquez sur **Gérer les connexions**.</span><span class="sxs-lookup"><span data-stu-id="a0252-108">In the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], on the **Master Data** tab, in the **Connect and Load** group, click the arrow under the **Connect** button and click **Manage Connections**.</span></span>  
  
2.  <span data-ttu-id="a0252-109">Dans la boîte de dialogue **Gérer les connexions** , dans la section **Nouvelle connexion** , cliquez sur **Créer une connexion**.</span><span class="sxs-lookup"><span data-stu-id="a0252-109">On the **Manage Connections** dialog box, in the **New connection** section, click **Create a new connection**.</span></span>  
  
3.  <span data-ttu-id="a0252-110">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a0252-110">Click **New**.</span></span>  
  
4.  <span data-ttu-id="a0252-111">Dans la boîte de dialogue **Ajouter une nouvelle connexion** , dans le champ **Description** , tapez une description pour votre connexion.</span><span class="sxs-lookup"><span data-stu-id="a0252-111">On the **Add New Connection** dialog box, in the **Description** field, type a description for your connection.</span></span> <span data-ttu-id="a0252-112">Cette connexion s’affiche lorsque vous cliquez sur la flèche sous le bouton **Se connecter** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="a0252-112">This connection will be displayed when you click the arrow under the **Connect** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="a0252-113">Dans la zone **Adresse du serveur MDS**, tapez l’URL de l’application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], par exemple http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="a0252-113">In the **MDS server address** box, type the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0252-114">Vérifiez que vous utilisez le nom d’ordinateur ; n’utilisez pas « localhost ».</span><span class="sxs-lookup"><span data-stu-id="a0252-114">Ensure that you use the computer name; do not use "localhost".</span></span>  
  
6.  <span data-ttu-id="a0252-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0252-115">Click **OK**.</span></span> <span data-ttu-id="a0252-116">Le nom est affiché dans la section **Connexions existantes** .</span><span class="sxs-lookup"><span data-stu-id="a0252-116">The name is displayed in the **Existing Connections** section.</span></span>  
  
7.  <span data-ttu-id="a0252-117">Vous pouvez également cliquer sur **Tester** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="a0252-117">Optionally, click **Test** to test the connection.</span></span> <span data-ttu-id="a0252-118">Une boîte de dialogue de confirmation ou d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="a0252-118">A confirmation or error dialog is displayed.</span></span> <span data-ttu-id="a0252-119">Cliquez sur **OK** pour la fermer.</span><span class="sxs-lookup"><span data-stu-id="a0252-119">Click **OK** to close it.</span></span>  
  
8.  <span data-ttu-id="a0252-120">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="a0252-120">Click **Connect**.</span></span> <span data-ttu-id="a0252-121">Le volet **Master Data Services** est affiché.</span><span class="sxs-lookup"><span data-stu-id="a0252-121">The **Master Data Services** pane is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a0252-122">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a0252-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="a0252-123">Charger des données MDS dans Excel</span><span class="sxs-lookup"><span data-stu-id="a0252-123">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)  
  
-   [<span data-ttu-id="a0252-124">Filtrer les données avant de charger &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a0252-124">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0252-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0252-125">See Also</span></span>  
 [<span data-ttu-id="a0252-126">Connexions &#40;Complément MDS pour Excel#41;</span><span class="sxs-lookup"><span data-stu-id="a0252-126">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
  
