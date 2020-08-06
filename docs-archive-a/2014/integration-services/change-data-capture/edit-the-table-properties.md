---
title: Modifier les propriétés d’une table | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- editTabProps
ms.assetid: 95ea72ba-8e40-4177-a963-0fb4d10c56e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1ba0809b99474704ec0e93e417a04d776bb26d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602968"
---
# <a name="edit-the-table-properties"></a><span data-ttu-id="956bc-102">Modifier les propriétés d'une table</span><span class="sxs-lookup"><span data-stu-id="956bc-102">Edit the Table Properties</span></span>
  <span data-ttu-id="956bc-103">Cette boîte de dialogue permet de modifier des colonnes spécifiques de la table sélectionnée où les modifications sont capturées.</span><span class="sxs-lookup"><span data-stu-id="956bc-103">Use this dialog box to edit the specific columns from the selected table where changes are being captured.</span></span> <span data-ttu-id="956bc-104">Vous pouvez également modifier les informations du **Rôle de sécurité** et de l' **Instance de capture** .</span><span class="sxs-lookup"><span data-stu-id="956bc-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
### <a name="to-edit-the-columns-to-include-in-the-cdc-instance"></a><span data-ttu-id="956bc-105">Pour modifier les colonnes à inclure dans l'instance CDC.</span><span class="sxs-lookup"><span data-stu-id="956bc-105">To edit the columns to include in the CDC instance</span></span>  
  
1.  <span data-ttu-id="956bc-106">Effectuez une des actions suivantes ou les deux :</span><span class="sxs-lookup"><span data-stu-id="956bc-106">Do one or both of the following:</span></span>  
  
    -   <span data-ttu-id="956bc-107">Activez la case à cocher en regard des colonnes supplémentaires à inclure.</span><span class="sxs-lookup"><span data-stu-id="956bc-107">Select the check box next to any additional column you want to include.</span></span>  
  
    -   <span data-ttu-id="956bc-108">Désactivez la case à cocher en regard des colonnes que vous ne souhaitez plus inclure.</span><span class="sxs-lookup"><span data-stu-id="956bc-108">Clear the check box next to any column that you no longer want to include.</span></span>  
  
### <a name="to-edit-the-security-role"></a><span data-ttu-id="956bc-109">Pour modifier le rôle de sécurité</span><span class="sxs-lookup"><span data-stu-id="956bc-109">To edit the Security Role</span></span>  
  
1.  <span data-ttu-id="956bc-110">Tapez un nouveau nom ou modifiez le nom du rôle de sécurité dans le champ **Rôle de sécurité** .</span><span class="sxs-lookup"><span data-stu-id="956bc-110">Type a new name or edit the name of the security role in the **Security Role** field.</span></span>  
  
### <a name="to-create-a-new-capture-instance"></a><span data-ttu-id="956bc-111">Pour créer une instance de capture</span><span class="sxs-lookup"><span data-stu-id="956bc-111">To create a new capture instance</span></span>  
  
1.  <span data-ttu-id="956bc-112">Dans le champ **Nom** de la section **Rôle de sécurité** entrez un nom pour l'instance de capture.</span><span class="sxs-lookup"><span data-stu-id="956bc-112">In the **Security Role** section, **Name** field enter a name for the capture instance.</span></span> <span data-ttu-id="956bc-113">Par défaut, le nom entré dans le champ est le nom de l’instance de capture actuelle avec **_NEW** ajouté à la fin du nom (par exemple, **ancienne_instance_NEW**).</span><span class="sxs-lookup"><span data-stu-id="956bc-113">By default, the name entered in the field is the name of the current capture instance with **_NEW** added to the end of the name (for example, **old_instance_NEW**).</span></span>  
  
2.  <span data-ttu-id="956bc-114">Enregistrez l'instance de capture comme un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="956bc-114">Save the capture instance as one of the following:</span></span>  
  
    -   <span data-ttu-id="956bc-115">**Nouvelle instance de capture**: dans ce cas, une nouvelle instance de capture est enregistrée et l'ancienne instance de capture n'est pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="956bc-115">**New Capture Instance**: In this case a new capture instance is saved and the old capture instance is not deleted.</span></span>  
  
         <span data-ttu-id="956bc-116">**Remarque**: vous ne pouvez pas avoir plus de deux instances de capture par table.</span><span class="sxs-lookup"><span data-stu-id="956bc-116">**Note**: You can have no more than two capture instances per table.</span></span> <span data-ttu-id="956bc-117">S'il existe déjà deux instances de capture, cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="956bc-117">If there are already two capture instances, this option is not available.</span></span>  
  
    -   <span data-ttu-id="956bc-118">**Remplacer l'instance de capture existante**: dans ce cas, l'instance de capture actuelle est supprimée et remplacée par l'instance de capture que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="956bc-118">**Replace Existing**: In this case the current capture instance is deleted and replaced by the capture instance you created.</span></span> <span data-ttu-id="956bc-119">Si deux instances de capture sont définies pour cette table, vous devez en sélectionner une à remplacer.</span><span class="sxs-lookup"><span data-stu-id="956bc-119">If there are two capture instances defined for this table, you must select one to replace.</span></span>  
  
 <span data-ttu-id="956bc-120">**Remarque**: vous pouvez supprimer une instance de capture de la liste des tables sous l'onglet **Table** .</span><span class="sxs-lookup"><span data-stu-id="956bc-120">**Note**: You can remove a capture instance from the list of tables in the **Table** tab.</span></span>  
  
 <span data-ttu-id="956bc-121">Une fois les informations entrées dans cette boîte de dialogue, cliquez sur **OK** pour accepter les modifications.</span><span class="sxs-lookup"><span data-stu-id="956bc-121">After you finish entering the information in this dialog box, click **OK** to accept the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956bc-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="956bc-122">See Also</span></span>  
 <span data-ttu-id="956bc-123">[Procédure : modifier les propriétés d'une instance de capture de données modifiées](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="956bc-123">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="956bc-124">Apporter des modifications aux tables sélectionnées pour capturer les modifications</span><span class="sxs-lookup"><span data-stu-id="956bc-124">Make Changes to the Tables Selected for Capturing Changes</span></span>](make-changes-to-the-tables-selected-for-capturing-changes.md)  
  
  
