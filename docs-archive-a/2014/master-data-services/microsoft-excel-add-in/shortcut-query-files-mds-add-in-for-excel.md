---
title: Fichiers de requête de raccourci (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 1ba0219a-6c40-41fa-aff9-8c8f41ef3220
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe1bdbdadabe0e6448ed3bdc65316104fb26ba43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698370"
---
# <a name="shortcut-query-files-mds-add-in-for-excel"></a><span data-ttu-id="9ccec-102">Fichiers de requête de raccourci (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="9ccec-102">Shortcut Query Files (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="9ccec-103">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], utilisez les fichiers de requête de raccourci pour rapidement vous connecter et charger les données fréquemment utilisées.</span><span class="sxs-lookup"><span data-stu-id="9ccec-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use shortcut query files to quickly connect and load frequently-used data.</span></span> <span data-ttu-id="9ccec-104">Vous pouvez également utiliser ces fichiers lorsque vous souhaitez partager des données MDS avec d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9ccec-104">You can also use them when you want to share MDS data with others.</span></span> <span data-ttu-id="9ccec-105">Au lieu d'enregistrer la feuille de calcul et de l'envoyer par courrier électronique, vous pouvez enregistrer un fichier de requête de raccourci et l'envoyer de la même manière.</span><span class="sxs-lookup"><span data-stu-id="9ccec-105">Instead of saving the worksheet and emailing it, you should save a shortcut query file and email that instead.</span></span> <span data-ttu-id="9ccec-106">De cette façon, vous êtes sûr que votre destinataire et vous-même êtes connectés au référentiel MDS pour récupérer les données les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="9ccec-106">This ensures that you are both connecting to the MDS repository to get the latest data.</span></span>  
  
 <span data-ttu-id="9ccec-107">Les fichiers de requête de raccourci sont des fichiers XML qui contiennent des informations sur :</span><span class="sxs-lookup"><span data-stu-id="9ccec-107">Shortcut query files are XML files that contain information about:</span></span>  
  
-   <span data-ttu-id="9ccec-108">la connexion au référentiel MDS ;</span><span class="sxs-lookup"><span data-stu-id="9ccec-108">The MDS repository connection.</span></span>  
  
-   <span data-ttu-id="9ccec-109">le modèle, la version, et l'entité ;</span><span class="sxs-lookup"><span data-stu-id="9ccec-109">The model, version, and entity.</span></span>  
  
-   <span data-ttu-id="9ccec-110">tous les filtres appliqués lorsque le raccourci a été créé ;</span><span class="sxs-lookup"><span data-stu-id="9ccec-110">Any filters that were applied when the shortcut was created.</span></span>  
  
-   <span data-ttu-id="9ccec-111">l'ordre de gauche à droite des colonnes lorsque le raccourci a été créé.</span><span class="sxs-lookup"><span data-stu-id="9ccec-111">The left-to-right order of the columns when the shortcut was created.</span></span>  
  
 <span data-ttu-id="9ccec-112">Vous pouvez enregistrer ces fichiers dans une liste et les choisir lorsque vous ouvrez le complément.</span><span class="sxs-lookup"><span data-stu-id="9ccec-112">You can save these files in a list and choose from them when you open the Add-in.</span></span> <span data-ttu-id="9ccec-113">Vous pouvez les exporter sur votre ordinateur ou dans un emplacement partagé, ou vous pouvez les envoyer à d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9ccec-113">You can export them to your computer or to a shared location, or you can send them to others.</span></span>  
  
## <a name="queryopener-application"></a><span data-ttu-id="9ccec-114">Application QueryOpener</span><span class="sxs-lookup"><span data-stu-id="9ccec-114">QueryOpener Application</span></span>  
 <span data-ttu-id="9ccec-115">Tous les utilisateurs qui installent [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] installent également une application appelée QueryOpener.</span><span class="sxs-lookup"><span data-stu-id="9ccec-115">All users who install the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] have an application called QueryOpener installed.</span></span> <span data-ttu-id="9ccec-116">Cette application sert à ouvrir des fichiers de requête de raccourci dans [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ccec-116">This application is used to open shortcut query files in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span></span> <span data-ttu-id="9ccec-117">Si vous double-cliquez sur le fichier de requête de raccourci, cette application est automatiquement lancée pour ouvrir le fichier dans le complément.</span><span class="sxs-lookup"><span data-stu-id="9ccec-117">If you double-click a shortcut query file, this application is automatically used to open the file in the Add-in.</span></span>  
  
 <span data-ttu-id="9ccec-118">Quand vous ouvrez un fichier de requête de raccourci avec cette application, vous êtes invité à créer une connexion « sécurisée », indiquant que vous faites confiance au contenu de cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="9ccec-118">When you open a shortcut query file with this application, you are prompted to make the connection a "safe" connection, which means you trust content from this location.</span></span> <span data-ttu-id="9ccec-119">Chaque fois que vous marquez une connexion comme sécurisée, elle est ajouté à la liste.</span><span class="sxs-lookup"><span data-stu-id="9ccec-119">Each time you mark a connection as safe, it is added to a list.</span></span> <span data-ttu-id="9ccec-120">Si vous souhaitez effacer cette liste, ouvrez la boîte de dialogue **Paramètres** , puis dans la section **Serveurs ajoutés à la liste sécurisée** , cliquez sur **Effacer tout**.</span><span class="sxs-lookup"><span data-stu-id="9ccec-120">If you want to clear this list, open the **Settings** dialog box and in the **Servers Added to Safe List** section, click **Clear All**.</span></span>  
  
 <span data-ttu-id="9ccec-121">L’emplacement par défaut de l’application est *lecteur*: \Program Files\Microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span><span class="sxs-lookup"><span data-stu-id="9ccec-121">The default location for the application is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span></span>  
  
 <span data-ttu-id="9ccec-122">Il existe deux manières d'ouvrir des fichiers de requête de raccourci : vous pouvez les importer ou bien double-cliquer sur leur icône pour les ouvrir automatiquement.</span><span class="sxs-lookup"><span data-stu-id="9ccec-122">There are two ways to open shortcut query files: you can import them or you can double-click them and they are opened automatically.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9ccec-123">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9ccec-123">Related Tasks</span></span>  
  
|<span data-ttu-id="9ccec-124">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="9ccec-124">Task Description</span></span>|<span data-ttu-id="9ccec-125">Rubrique</span><span class="sxs-lookup"><span data-stu-id="9ccec-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="9ccec-126">Enregistrez le contenu de la feuille de calcul active en tant que fichier de requête de raccourci.</span><span class="sxs-lookup"><span data-stu-id="9ccec-126">Save the contents of the active worksheet as a shortcut query file.</span></span>|[<span data-ttu-id="9ccec-127">Enregistrer un fichier de requête de raccourci &#40;Complément MDS pour Excel#41;</span><span class="sxs-lookup"><span data-stu-id="9ccec-127">Save a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](save-a-shortcut-query-file-mds-add-in-for-excel.md)|  
|<span data-ttu-id="9ccec-128">Envoyez par courrier électronique un fichier de requête de raccourci qui représente le contenu de la feuille de calcul active.</span><span class="sxs-lookup"><span data-stu-id="9ccec-128">Email a shortcut query file that represents the contents of the active worksheet.</span></span>|[<span data-ttu-id="9ccec-129">Envoyer par e-mail un fichier de requête de raccourci &#40;Complément MDS pour Excel#41;</span><span class="sxs-lookup"><span data-stu-id="9ccec-129">Email a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](email-a-shortcut-query-file-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="9ccec-130">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="9ccec-130">Related Content</span></span>  
  
-   [<span data-ttu-id="9ccec-131">Connexions &#40;Complément MDS pour Excel#41;</span><span class="sxs-lookup"><span data-stu-id="9ccec-131">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="9ccec-132">Complément Master Data Services pour Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="9ccec-132">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
-   [<span data-ttu-id="9ccec-133">Sécurité &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9ccec-133">Security &#40;Master Data Services&#41;</span></span>](../security-master-data-services.md)  
  
  
