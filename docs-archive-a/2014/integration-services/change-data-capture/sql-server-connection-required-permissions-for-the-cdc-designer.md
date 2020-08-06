---
title: Autorisations de connexion SQL Server requises pour CDC Designer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80334de2-17c1-43c9-951e-21a9f864e9cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0815a5d8f1cb66dee0d290a45166ebb395c8efa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601029"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-designer"></a><span data-ttu-id="35bde-102">Autorisations de connexion SQL Server requises pour le concepteur CDC</span><span class="sxs-lookup"><span data-stu-id="35bde-102">SQL Server Connection Required Permissions for the CDC Designer</span></span>
  <span data-ttu-id="35bde-103">La console du concepteur CDC nécessite des informations de connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour effectuer ses tâches.</span><span class="sxs-lookup"><span data-stu-id="35bde-103">The CDC Designer Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform its tasks.</span></span> <span data-ttu-id="35bde-104">Cette rubrique décrit les informations qui peuvent être fournies dans la boîte de dialogue **Connexion à SQL Server** pour configurer la connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35bde-104">This topic describes the information that can be provided in the **Connect to SQL Server** dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="35bde-105">La boîte de dialogue **Connexion à SQL Server** s'affiche si nécessaire, par exemple lorsque les informations de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne sont pas disponibles ou lorsque les informations existent mais que la connexion ne dispose pas des autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="35bde-105">The **Connect to SQL Server** dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="35bde-106">Le tableau suivant décrit les différentes tâches nécessitant une connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ainsi que les autorisations que doit avoir la connexion ou l’utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="35bde-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="35bde-107">Tâche</span><span class="sxs-lookup"><span data-stu-id="35bde-107">Task</span></span>|<span data-ttu-id="35bde-108">Autorisations minimales</span><span class="sxs-lookup"><span data-stu-id="35bde-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="35bde-109">Afficher la liste des services et des instances de capture de données modifiées à l'aide de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associée.</span><span class="sxs-lookup"><span data-stu-id="35bde-109">View the list of CDC Services and Instances using the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>|<span data-ttu-id="35bde-110">`db_datareader` sur MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="35bde-110">`db_datareader` role on MSXDBCDC</span></span>|  
|<span data-ttu-id="35bde-111">Démarrer/arrêter une ou plusieurs instances de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="35bde-111">Start/Stop CDC Instance(s)</span></span>|<span data-ttu-id="35bde-112">`db_datareader` et `db_datawriter` sur MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="35bde-112">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="35bde-113">Afficher l'état d'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="35bde-113">View the CDC Instance status.</span></span>|<span data-ttu-id="35bde-114">`db_owner` sur la base de données d'instance de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="35bde-114">`db_owner` role on the CDC Instance database</span></span>|  
|<span data-ttu-id="35bde-115">Créer une base de données d'instance Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="35bde-115">Create a new Oracle CDC Instance database.</span></span>|<span data-ttu-id="35bde-116">`dbcreator` rôle serveur fixe</span><span class="sxs-lookup"><span data-stu-id="35bde-116">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="35bde-117">Créer une instance Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="35bde-117">Create a new Oracle CDC Instance.</span></span>|<span data-ttu-id="35bde-118">`db_datareader` sur MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="35bde-118">`db_datareader` role on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="35bde-119">`db_owner` sur la base de données CDC créée.</span><span class="sxs-lookup"><span data-stu-id="35bde-119">`db_owner` role on the CDC database that was created.</span></span>|  
|<span data-ttu-id="35bde-120">Obtenir des scripts de déploiement.</span><span class="sxs-lookup"><span data-stu-id="35bde-120">Get deployment scripts.</span></span>|<span data-ttu-id="35bde-121">`db_datareader` et `db_datawriter` sur MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="35bde-121">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="35bde-122">`db_owner` sur la base de données CDC associée</span><span class="sxs-lookup"><span data-stu-id="35bde-122">`db_owner` role on the relatedCDC database</span></span>|  
|<span data-ttu-id="35bde-123">Modifier la configuration et ajouter/supprimer des instances de capture.</span><span class="sxs-lookup"><span data-stu-id="35bde-123">Change configuration and add/remove capture instances.</span></span>|<span data-ttu-id="35bde-124">`db_datareader` et `db_datawriter` sur MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="35bde-124">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="35bde-125">`db_owner` sur la base de données CDC associée</span><span class="sxs-lookup"><span data-stu-id="35bde-125">`db_owner` role on the related CDC database</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35bde-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35bde-126">See Also</span></span>  
 <span data-ttu-id="35bde-127">[Accéder à la console du concepteur CDC](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="35bde-127">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="35bde-128">Connexion SQL Server pour la création d’une instance</span><span class="sxs-lookup"><span data-stu-id="35bde-128">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
