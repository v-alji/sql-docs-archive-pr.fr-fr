---
title: Autorisations de connexion SQL Server requises pour le service CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9e968f9-180c-4fa0-a849-98f2b1942330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e63b98ffd0371bd5b70ecc0ac843ad40a4a5d03e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604085"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-service"></a><span data-ttu-id="0173c-102">Autorisations de connexion SQL Server requises pour le service de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="0173c-102">SQL Server Connection Required Permissions for the CDC Service</span></span>
  <span data-ttu-id="0173c-103">La console de configuration du service de capture de données modifiées requiert des informations de connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour effectuer ses tâches.</span><span class="sxs-lookup"><span data-stu-id="0173c-103">The CDC Service Configuration Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform their tasks.</span></span> <span data-ttu-id="0173c-104">Cette rubrique décrit les informations qui peuvent être fournies dans la boîte de dialogue Connexion à SQL Server pour configurer la connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0173c-104">This topic describes the information that can be provided in the Connect to SQL Server dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0173c-105">La boîte de dialogue Connexion à SQL Server s'affiche si nécessaire, par exemple lorsque les informations de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne sont pas disponibles ou lorsque les informations existent mais que la connexion ne dispose pas des autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="0173c-105">The Connect to SQL Server dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="0173c-106">Le tableau suivant décrit les différentes tâches nécessitant une connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ainsi que les autorisations que doit avoir la connexion ou l’utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0173c-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="0173c-107">Tâche</span><span class="sxs-lookup"><span data-stu-id="0173c-107">Task</span></span>|<span data-ttu-id="0173c-108">Autorisations minimales</span><span class="sxs-lookup"><span data-stu-id="0173c-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="0173c-109">Préparer une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0173c-109">Prepare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance.</span></span>|<span data-ttu-id="0173c-110">`dbcreator` rôle serveur fixe</span><span class="sxs-lookup"><span data-stu-id="0173c-110">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="0173c-111">Créer une connexion SQL Server de service de capture de données modifiées Oracle en vue d'une utilisation par le service de capture de données modifiées Oracle.</span><span class="sxs-lookup"><span data-stu-id="0173c-111">Create an Oracle CDC Service-SQL Server login for use by the Oracle CDC service.</span></span>|<span data-ttu-id="0173c-112">`public` rôle serveur fixe</span><span class="sxs-lookup"><span data-stu-id="0173c-112">`public` fixed-server role</span></span>|  
|<span data-ttu-id="0173c-113">Créer une connexion de service de capture de données modifiées Oracle à utiliser pour inscrire le nouveau service dans MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0173c-113">Create an Oracle CDC Service-login to use for registering the new service in MSXDBCDC.</span></span>|<span data-ttu-id="0173c-114">`db_datareader` et `db_datawriter` sur MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="0173c-114">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="0173c-115">Modifier une connexion de service de capture de données modifiées Oracle en vue d'une utilisation pour la mise à jour de l'inscription du service dans MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0173c-115">Edit an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="0173c-116">`db_datareader` et `db_datawriter` sur MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="0173c-116">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="0173c-117">Supprimer une connexion de service de capture de données modifiées Oracle en vue d'une utilisation pour la mise à jour de l'inscription du service dans MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0173c-117">Delete an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="0173c-118">`db_datareader` et `db_datawriter` sur MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="0173c-118">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0173c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0173c-119">See Also</span></span>  
 <span data-ttu-id="0173c-120">[Connexion à SQL Server](connection-to-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0173c-120">[Connection to SQL Server](connection-to-sql-server.md) </span></span>  
 [<span data-ttu-id="0173c-121">Connexion à SQL Server pour la suppression</span><span class="sxs-lookup"><span data-stu-id="0173c-121">Connection to SQL Server for Delete</span></span>](connection-to-sql-server-for-delete.md)  
  
  
