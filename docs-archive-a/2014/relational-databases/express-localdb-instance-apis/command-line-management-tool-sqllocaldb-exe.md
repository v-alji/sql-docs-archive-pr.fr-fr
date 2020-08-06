---
title: 'Outil de gestion en ligne de commande : SqlLocalDB.exe | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: dd0882b1-a8a9-447a-8bdf-0f9d7f36d336
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d21a6a8879e981e52bd2e7d3bd05a37e65d8cf4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601477"
---
# <a name="command-line-management-tool-sqllocaldbexe"></a><span data-ttu-id="5f8ef-102">Outil de gestion en ligne de commande : SqlLocalDB.exe</span><span class="sxs-lookup"><span data-stu-id="5f8ef-102">Command-Line Management Tool: SqlLocalDB.exe</span></span>
  <span data-ttu-id="5f8ef-103">SqlLocalDB.exe est un outil simple qui permet à l'utilisateur de gérer facilement les instances de LocalDB à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-103">SqlLocalDB.exe is a simple tool that enables the user to easily manage LocalDB instances from the command line.</span></span> <span data-ttu-id="5f8ef-104">Il est implémenté comme wrapper simple autour de l'API de l'instance de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-104">It is implemented as a simple wrapper around the LocalDB instance API.</span></span> <span data-ttu-id="5f8ef-105">Comme dans de nombreux outils similaires SQL Server (par exemple, SQLCMD), les paramètres sont passés à SqlLocalDB comme arguments de ligne de commande et la sortie est envoyée à la console.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-105">As in many similar SQL Server tools (for example, SQLCMD), parameters are passed to SqlLocalDB as command-line arguments and output is sent to the console.</span></span>  
  
 <span data-ttu-id="5f8ef-106">SqlLocalDB permet aux développeurs d'utiliser LocalDB sans devoir écrire du code pour appeler l'API ou dépendre d'autres d'outils pour l'exécuter pour eux.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-106">SqlLocalDB enables developers to use LocalDB without having to write code to call the API or depend on other tools to do it for them.</span></span>  
  
## <a name="sqllocaldb-options"></a><span data-ttu-id="5f8ef-107">Options de SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="5f8ef-107">SqlLocalDB Options</span></span>  
 <span data-ttu-id="5f8ef-108">SqlLocalDB prend en charge les options suivantes.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-108">SqlLocalDB supports the following options.</span></span>  
  
|<span data-ttu-id="5f8ef-109">Option</span><span class="sxs-lookup"><span data-stu-id="5f8ef-109">Option</span></span>|<span data-ttu-id="5f8ef-110">Résultat</span><span class="sxs-lookup"><span data-stu-id="5f8ef-110">What it does</span></span>|  
|------------|------------------|  
|`-?`|<span data-ttu-id="5f8ef-111">Affiche le texte d'aide.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-111">Prints help text.</span></span>|  
|`create&#124;c "instance name" [version-number] [-s]`|<span data-ttu-id="5f8ef-112">Crée une nouvelle instance de LocalDB avec un nom et une version spécifiés.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-112">Creates a new LocalDB instance with a specified name and version.</span></span><br /><br /> <span data-ttu-id="5f8ef-113">Si le paramètre [numéro-version] est omis, il prend par défaut la valeur de la version de la build de SqlLocalDB.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-113">If the [version-number] parameter is omitted, it defaults to the SqlLocalDB build version.</span></span><br /><br /> <span data-ttu-id="5f8ef-114">-s démarre la nouvelle instance de LocalDB après sa création.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-114">-s starts the new LocalDB instance after it is created.</span></span>|  
|`delete&#124;d "instance name"`|<span data-ttu-id="5f8ef-115">Supprime l'instance de LocalDB portant le nom spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-115">Deletes the LocalDB instance with the specified name.</span></span>|  
|`start&#124;s "instance name"`|<span data-ttu-id="5f8ef-116">Démarre l'instance de LocalDB portant le nom spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-116">Starts the LocalDB instance with the specified name.</span></span>|  
|`stop&#124;p "instance name" [-i&#124;-k]`|<span data-ttu-id="5f8ef-117">Arrête l'instance de LocalDB portant le nom spécifié, une fois les requêtes actuelles terminées.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-117">Stops the LocalDB instance with the specified name, after current queries finish running.</span></span><br /><br /> <span data-ttu-id="5f8ef-118">-i demande l'arrêt de l'instance de LocalDB avec l'option NOWAIT.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-118">-i requests the LocalDB instance shutdown with the NOWAIT option.</span></span><br /><br /> <span data-ttu-id="5f8ef-119">-k met fin au processus de l'instance de LocalDB sans le contacter.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-119">-k kills the LocalDB instance process without contacting it.</span></span>|  
|`share&#124;h ["owner SID or account"] "private name" "shared name"`|<span data-ttu-id="5f8ef-120">Partage l'instance privée spécifiée à l'aide du nom partagé spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-120">Shares the specified private instance using the specified shared name.</span></span> <span data-ttu-id="5f8ef-121">Si le SID ou le nom de compte de l'utilisateur est omis, il prend par défaut la valeur de l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-121">If the user SID or account name is omitted, it defaults to the current user.</span></span>|  
|`unshare&#124;u "shared name"`|<span data-ttu-id="5f8ef-122">Annule le partage de l'instance de LocalDB partagée spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-122">Unshares the specified shared LocalDB instance.</span></span>|  
|`info&#124;i`|<span data-ttu-id="5f8ef-123">Répertorie toutes les instances existantes de LocalDB détenues par l'utilisateur actuel et toutes les instances partagées de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-123">Lists all existing LocalDB instances that are owned by the current user and all shared LocalDB instances.</span></span>|  
|`info&#124;i "instance name"`|<span data-ttu-id="5f8ef-124">Affiche des informations relatives à l'instance de LocalDB spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-124">Prints the information about the specified LocalDB instance.</span></span>|  
|`versions&#124;v`|<span data-ttu-id="5f8ef-125">Répertorie toutes les versions de LocalDB installées sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-125">Lists all LocalDB versions installed on the computer.</span></span>|  
|||  
|`trace&#124;t on&#124;off`|<span data-ttu-id="5f8ef-126">Active et désactive le traçage.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-126">Turns tracing on and off.</span></span>|  
  
 <span data-ttu-id="5f8ef-127">SqlLocalDB traite les espaces comme des délimiteurs ; vous devez donc placer les noms d'instances contenant des espaces et des caractères spéciaux entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-127">SqlLocalDB treats spaces as delimiters; you must surround the instance names that contain spaces and special characters with quotes.</span></span> <span data-ttu-id="5f8ef-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5f8ef-128">For example:</span></span>  
  
 `SqlLocalDB create "My instance name with spaces"`  
  
  
