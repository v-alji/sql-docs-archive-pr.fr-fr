---
title: Supprimer les objets | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.deleteobjects.f1
helpviewer_keywords:
- Delete Objects dialog box
ms.assetid: 49541441-179c-40d3-ba0c-01bcae545984
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7b20d1eee3e48c5531b6b788e125b943f7606d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599768"
---
# <a name="delete-objects"></a><span data-ttu-id="66025-102">Supprimer les objets</span><span class="sxs-lookup"><span data-stu-id="66025-102">Delete Objects</span></span>
  <span data-ttu-id="66025-103">Cette boîte de dialogue vous permet de supprimer une base de données ou un objet de base de données.</span><span class="sxs-lookup"><span data-stu-id="66025-103">Use this dialog box to delete a database or database object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="66025-104">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="66025-104">UI element list</span></span>  
 <span data-ttu-id="66025-105">**Objet à supprimer**</span><span class="sxs-lookup"><span data-stu-id="66025-105">**Object to be deleted**</span></span>  
 <span data-ttu-id="66025-106">Indique les noms, les types, les propriétaires et l'état des objets qui seront supprimés, ainsi que tous les messages sur les erreurs au cours de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="66025-106">Displays the names, types, owners, and status of the objects that are about to be deleted, as well as any messages about errors during execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66025-107">Exécuter **Supprimer** sur une base de données équivaut à exécuter DROP DATABASE dans [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66025-107">Running **Delete** on a database is equivalent to issuing DROP DATABASE in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="66025-108">**Afficher les dépendances**</span><span class="sxs-lookup"><span data-stu-id="66025-108">**Show Dependencies**</span></span>  
 <span data-ttu-id="66025-109">Cliquez ici pour afficher à la fois les objets qui dépendent de l'objet actuellement sélectionné et les objets dont dépend l'objet actuel (dépendance ascendante et descendante).</span><span class="sxs-lookup"><span data-stu-id="66025-109">Click to display both the objects that are dependent on the currently selected object and objects that the current object is dependent on (upward and downward dependency).</span></span> <span data-ttu-id="66025-110">Les informations affichées dans la boîte de dialogue **Afficher les dépendances** sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="66025-110">The information displayed in the **Show Dependencies** dialog box is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66025-111">Le bouton **Afficher les dépendances** n'est pas affiché pour tous les types d'objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="66025-111">The **Show Dependencies** button does not appear for all types of database objects.</span></span> <span data-ttu-id="66025-112">Pour afficher les dépendances quand le bouton **Afficher les dépendances** n’est pas disponible, cliquez avec le bouton droit sur l’objet dans l’Explorateur d’objets, puis cliquez sur **Afficher les dépendances**.</span><span class="sxs-lookup"><span data-stu-id="66025-112">To view dependencies when the **Show Dependencies** button is not available, right-click the object in Object Explorer, and then click **View Dependencies**.</span></span>  
  
 <span data-ttu-id="66025-113">**Supprimer les informations d'historique de sauvegarde et de restauration pour les bases de données**</span><span class="sxs-lookup"><span data-stu-id="66025-113">**Delete backup and restore history information for databases**</span></span>  
 <span data-ttu-id="66025-114">Cette case à cocher apparaît seulement quand une base de données est supprimée et elle permet de supprimer l’historique de sauvegarde et de restauration pour la base de données d’objet dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="66025-114">Only appears when a database is deleted, this check box causes the backup and restore history for the subject database to be deleted from the **msdb** database.</span></span>  
  
 <span data-ttu-id="66025-115">**Fermer les connexions existantes**</span><span class="sxs-lookup"><span data-stu-id="66025-115">**Close existing connections**</span></span>  
 <span data-ttu-id="66025-116">Cette case à cocher apparaît seulement lorsqu'une base de données est supprimée et elle permet de mettre fin aux connexions à la base de données d'objet.</span><span class="sxs-lookup"><span data-stu-id="66025-116">Only appears when a database is deleted, this check box terminates connections to the subject database.</span></span>  
  
  
