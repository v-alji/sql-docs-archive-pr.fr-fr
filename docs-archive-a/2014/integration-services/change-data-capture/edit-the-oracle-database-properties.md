---
title: Modifier les propriétés d’une base de données Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraProp
ms.assetid: 58dc99f1-ee6b-4508-bb66-2bc589611ff7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3cad2735e6cd6095f9730f3b4e7228526451d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603587"
---
# <a name="edit-the-oracle-database-properties"></a><span data-ttu-id="a93b6-102">Modifier les propriétés d'une base de données Oracle</span><span class="sxs-lookup"><span data-stu-id="a93b6-102">Edit the Oracle Database Properties</span></span>
  <span data-ttu-id="a93b6-103">Utilisez l'onglet Oracle de l'éditeur de propriétés pour apporter des modifications à la description que vous avez fournie dans la page Créer une base de données CDC de l'Assistant Nouvelle instance et pour apporter des modifications aux informations de connexion à la base de données d'exploration de données de journaux Oracle.</span><span class="sxs-lookup"><span data-stu-id="a93b6-103">Use the Oracle tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
 <span data-ttu-id="a93b6-104">La section suivante décrit les informations présentes dans l'onglet **Oracle** .</span><span class="sxs-lookup"><span data-stu-id="a93b6-104">The following describes the information in the **Oracle** tab.</span></span>  
  
 <span data-ttu-id="a93b6-105">**Nom**</span><span class="sxs-lookup"><span data-stu-id="a93b6-105">**Name**</span></span>  
 <span data-ttu-id="a93b6-106">Nom de l'instance de capture de données modifiées entré dans la page Créer une base de données CDC de l'Assistant Nouvelle instance.</span><span class="sxs-lookup"><span data-stu-id="a93b6-106">The name of the CDC Instance that you entered in the Create CDC Database page in the New Instance wizard.</span></span> <span data-ttu-id="a93b6-107">Ce champ est en lecture seule et vous ne pouvez pas modifier ces informations.</span><span class="sxs-lookup"><span data-stu-id="a93b6-107">This field is read only and you cannot edit this information.</span></span>  
  
 <span data-ttu-id="a93b6-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a93b6-108">**Description**</span></span>  
 <span data-ttu-id="a93b6-109">Vous pouvez modifier la description de la nouvelle instance ou en ajouter une si vous ne l'avez pas fait lors de la création de l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="a93b6-109">You can edit the description of the new instance or add one if you did not do so when creating the CDC Instance.</span></span>  
  
 <span data-ttu-id="a93b6-110">**Chaîne de connexion Oracle**</span><span class="sxs-lookup"><span data-stu-id="a93b6-110">**Oracle Connect String**</span></span>  
 <span data-ttu-id="a93b6-111">Chaîne de connexion Oracle à l'ordinateur sur lequel est installée la base de données Oracle que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="a93b6-111">The Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="a93b6-112">Ce champ est en lecture seule et vous ne pouvez pas modifier ces informations.</span><span class="sxs-lookup"><span data-stu-id="a93b6-112">This field is read only and you cannot edit this information.</span></span> <span data-ttu-id="a93b6-113">Cela est dû au fait que certaines modifications apportées à la chaîne de connexion peuvent faire pointer l’instance Oracle CDC vers une autre base de données Oracle, ce qui peut altérer l’état de l’instance de capture de données modifiées stocké dans la table **cdc.xdbcdc_config** .</span><span class="sxs-lookup"><span data-stu-id="a93b6-113">This is because some changes to the connect string may point the Oracle CDC Instance to another Oracle database entirely, corrupting the CDC Instance state as stored in the **cdc.xdbcdc_config** table.</span></span> <span data-ttu-id="a93b6-114">Si des modifications mineures sont nécessaires, vous pouvez modifier la chaîne de connexion directement dans la table de configuration à l'aide de SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="a93b6-114">If minor changes are needed, you can change the connect string directly in the configuration table using SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="a93b6-115">**Authentification pour l'exploration de données de journaux Oracle**</span><span class="sxs-lookup"><span data-stu-id="a93b6-115">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="a93b6-116">Pour entrer les informations d’identification pour la base de données Oracle qui contient l’outil Log Miner, sélectionnez une des options suivantes sous **Authentification**:</span><span class="sxs-lookup"><span data-stu-id="a93b6-116">To enter the authentication credentials for the Oracle database that contains the log miner, select one of the following under **Authentication**:</span></span>  
  
-   <span data-ttu-id="a93b6-117">**Authentification Windows**: sélectionnez cette option pour utiliser les informations d'identification actuelles de domaine Windows.</span><span class="sxs-lookup"><span data-stu-id="a93b6-117">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="a93b6-118">Vous ne pouvez utiliser cette option que si la base de données Oracle est configurée pour utiliser l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="a93b6-118">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="a93b6-119">**Authentification Oracle**: si vous sélectionnez cette option, vous devez taper le **Nom d'utilisateur** et le **Mot de passe** de l'utilisateur dans la base de données Oracle à laquelle vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="a93b6-119">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
 <span data-ttu-id="a93b6-120">Vous pouvez afficher les propriétés de base de données Oracle dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="a93b6-120">You can view the Oracle database properties in the viewer.</span></span> <span data-ttu-id="a93b6-121">Lorsque vous utilisez la visionneuse, les informations sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a93b6-121">When using the viewer the information is read only.</span></span> <span data-ttu-id="a93b6-122">La visionneuse inclut également la liste des colonnes capturées dans la table.</span><span class="sxs-lookup"><span data-stu-id="a93b6-122">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="a93b6-123">Pour plus d'informations sur l'accès à la visionneuse, consultez [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="a93b6-123">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93b6-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a93b6-124">See Also</span></span>  
 <span data-ttu-id="a93b6-125">[Procédure : gérer un service de capture de données modifiées à partir de la console du concepteur CDC](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="a93b6-125">[How to Manage a CDC Service from the CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span></span>  
 <span data-ttu-id="a93b6-126">[Se connecter à une base de données source Oracle](connect-to-an-oracle-source-database.md) </span><span class="sxs-lookup"><span data-stu-id="a93b6-126">[Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md) </span></span>  
 [<span data-ttu-id="a93b6-127">Se connecter à Oracle</span><span class="sxs-lookup"><span data-stu-id="a93b6-127">Connect to Oracle</span></span>](connect-to-oracle.md)  
  
  
