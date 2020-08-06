---
title: Se connecter au serveur (page Paramètres de connexion supplémentaires) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoserver.options.registeredservers.f1
ms.assetid: ba34b01a-6289-4eb8-8341-fa3d9ec87b3f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5c6a23df6a6b9ea324d54fd270f5aa2269471ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614827"
---
# <a name="connect-to-server-additional-connection-parameters-page"></a><span data-ttu-id="a6603-102">Se connecter au serveur (page Paramètes de connexion supplémentaires)</span><span class="sxs-lookup"><span data-stu-id="a6603-102">Connect to Server (Additional Connection Parameters Page)</span></span>
  <span data-ttu-id="a6603-103">La boîte de dialogue **Se connecter à** de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] présente les valeurs de chaîne de connexion les plus courantes sous forme d’options.</span><span class="sxs-lookup"><span data-stu-id="a6603-103">The **Connect to** dialog box of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] presents the most common connection string values as options.</span></span> <span data-ttu-id="a6603-104">Vous pouvez utiliser la page **Paramètres de connexion supplémentaires** pour ajouter d’autres paramètres de connexion à la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="a6603-104">Use the **Additional Connection Parameters** page to add more connection parameters to the connection string.</span></span>  
  
-   <span data-ttu-id="a6603-105">Les paramètres de connexion supplémentaires peuvent être n'importe quels paramètres de connexion ODBC.</span><span class="sxs-lookup"><span data-stu-id="a6603-105">Additional connection parameters can be any ODBC connection parameter.</span></span>  
  
-   <span data-ttu-id="a6603-106">Les paramètres de connexion supplémentaires doivent être ajoutés sous la forme **;paramètre1=valeur1;paramètres2=valeur2**.</span><span class="sxs-lookup"><span data-stu-id="a6603-106">Additional connection parameters should be added in the format **;parameter1=value1;parameter2=value2**.</span></span>  
  
-   <span data-ttu-id="a6603-107">Les paramètres ajoutés à partir de la page **Paramètres de connexion supplémentaires** sont ajoutés aux paramètres sélectionnés par le biais des options de la boîte de dialogue **Se connecter à** .</span><span class="sxs-lookup"><span data-stu-id="a6603-107">Parameters added using the **Additional Connection Parameters** page are added to the parameters selected using the **Connect to** dialog box options.</span></span>  
  
-   <span data-ttu-id="a6603-108">La dernière instance de chaque paramètre fourni remplace toutes les instances précédentes du paramètre.</span><span class="sxs-lookup"><span data-stu-id="a6603-108">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="a6603-109">Les paramètres ajoutés par le biais de la page **Paramètres de connexion supplémentaires** suivent et remplacent les paramètres fournis sous l’onglet **Connexion** ou **Propriétés de connexion** .</span><span class="sxs-lookup"><span data-stu-id="a6603-109">Parameters added using the **Additional Connection Parameters** page follow and replace the parameters provided in the **Login** or **Connection Properties** tabs.</span></span> <span data-ttu-id="a6603-110">Par exemple, si l’onglet **Connexion** fournit **SERVEUR1** comme **Nom du serveur**et si la page **Paramètres de connexion supplémentaires** indique **SERVEUR=SERVEUR2**, la connexion sera établie à **SERVEUR2**.</span><span class="sxs-lookup"><span data-stu-id="a6603-110">For example, if the **Login** tab provides **SERVER1** as the **Server name**, and the **Additional Connection Parameters** page contains **;SERVER=SERVER2**, the connection will be made to **SERVER2**.</span></span>  
  
-   <span data-ttu-id="a6603-111">Les paramètres ajoutés à l’aide de la page **Paramètres de connexion supplémentaires** sont toujours transmis sous forme de texte brut.</span><span class="sxs-lookup"><span data-stu-id="a6603-111">Parameters added using the **Additional Connection Parameters** page are always passed as plain text.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a6603-112">Évitez d’ajouter des informations d’identification de connexion et des mots de passe dans la page **Paramètres de connexion supplémentaires** .</span><span class="sxs-lookup"><span data-stu-id="a6603-112">Do not include login credentials and passwords in the **Additional Connection Parameters** page.</span></span> <span data-ttu-id="a6603-113">Ceux-ci ne seront pas chiffrés lorsqu'ils seront transmis sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="a6603-113">They will not be encrypted when they are passed across the network.</span></span> <span data-ttu-id="a6603-114">Utilisez pour cela l’onglet **Connexion** .</span><span class="sxs-lookup"><span data-stu-id="a6603-114">Use the **Login** tab instead.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a6603-115">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="a6603-115">Task List</span></span>  
  
### <a name="to-show-the-additional-connection-parameters-page"></a><span data-ttu-id="a6603-116">Pour afficher la page Paramètres de connexion supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a6603-116">To show the Additional Connection Parameters page</span></span>  
  
1.  <span data-ttu-id="a6603-117">Dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], dans le menu **Requête** , pointez sur **Connexion**, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="a6603-117">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Query** menu, point to **Connection**, and then click **Connect**.</span></span>  
  
2.  <span data-ttu-id="a6603-118">Dans la boîte de dialogue **Se connecter à** , cliquez sur **Options**, puis sur l’onglet **Paramètres de connexion supplémentaires** .</span><span class="sxs-lookup"><span data-stu-id="a6603-118">In the **Connect to** dialog box, click **Options**, and then click the **Additional Connection Parameters** tab.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a6603-119">Exemples</span><span class="sxs-lookup"><span data-stu-id="a6603-119">Examples</span></span>  
  
### <a name="example-a-connecting-to-the-database-engine"></a><span data-ttu-id="a6603-120">Exemple A : connexion au moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="a6603-120">Example A: Connecting to the Database Engine</span></span>  
 <span data-ttu-id="a6603-121">Pour vous connecter à la base de données [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] sur un serveur nommé ACCOUNTING, entrez la ligne suivante dans la page **Paramètres de connexion supplémentaires** :</span><span class="sxs-lookup"><span data-stu-id="a6603-121">To connect to the [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] database on a server named ACCOUNTING, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;SERVER=ACCOUNTING;DATABASE=AdventureWorks2012  
```  
  
### <a name="example-b-connecting-to-analysis-services"></a><span data-ttu-id="a6603-122">Exemple B : connexion à Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a6603-122">Example B: Connecting to Analysis Services</span></span>  
 <span data-ttu-id="a6603-123">Pour vous connecter à des serveurs d’analyse, définir un délai d’expiration de l’écriture différée de 5 et faire en sorte que toutes les partitions à l’écoute des notifications soient interrogées en temps réel (en évitant la mise en cache), entrez la ligne suivante dans la page **Paramètres connexion supplémentaires** :</span><span class="sxs-lookup"><span data-stu-id="a6603-123">To connect to the Analysis Servers and cause all the partitions listening for notifications to be queried as real time (bypassing caching), and to set the writeback time out value to 5, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;Real Time Olap=TRUE;Writeback Timeout=5  
```  
  
  
