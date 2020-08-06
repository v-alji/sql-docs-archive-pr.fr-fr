---
title: Options de validation d’abonnement (abonnements transactionnels) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.options.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: fd66ad1f-df01-4240-9e89-8f41bff12c1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 40a617dd1beff24f8f072f5d139bec7c1ca65f33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709115"
---
# <a name="subscription-validation-options-transactional-subscriptions"></a><span data-ttu-id="36e82-102">Options de validation d'abonnement (abonnements transactionnels)</span><span class="sxs-lookup"><span data-stu-id="36e82-102">Subscription Validation Options (Transactional Subscriptions)</span></span>
  <span data-ttu-id="36e82-103">Utilisez la boîte de dialogue **Options de validation d'abonnement** pour spécifier si la validation doit utiliser uniquement un nombre de lignes ou un nombre de lignes et une somme de contrôle binaire.</span><span class="sxs-lookup"><span data-stu-id="36e82-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only, or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="36e82-104">Options</span><span class="sxs-lookup"><span data-stu-id="36e82-104">Options</span></span>  
 <span data-ttu-id="36e82-105">**Vérifiez si l'abonné possède le même nombre de lignes de données répliquées que le serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="36e82-105">**Verify that the Subscriber has the same number of rows of replicated data as the Publisher**</span></span>  
 <span data-ttu-id="36e82-106">Sélectionnez le type de validation du nombre de lignes à effectuer.</span><span class="sxs-lookup"><span data-stu-id="36e82-106">Select the type of row count validation to perform.</span></span> <span data-ttu-id="36e82-107">Pour les publications Oracle, la seule option proposée est **Calculer le nombre réel de lignes en interrogeant directement les tables**.</span><span class="sxs-lookup"><span data-stu-id="36e82-107">For Oracle publications, the only available option is **Compute an actual row count by querying the tables directly**.</span></span>  
  
 <span data-ttu-id="36e82-108">**Comparer les sommes de contrôle pour vérifier les données de ligne**</span><span class="sxs-lookup"><span data-stu-id="36e82-108">**Compare checksums to verify row data**</span></span>  
 <span data-ttu-id="36e82-109">Outre le comptage des lignes sur le serveur de publication et sur l'Abonné, une somme de contrôle de toutes les données est calculée à l'aide de l'algorithme de somme de contrôle binaire.</span><span class="sxs-lookup"><span data-stu-id="36e82-109">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="36e82-110">Si le nombre de lignes est erroné, la somme de contrôle n'est pas effectuée.</span><span class="sxs-lookup"><span data-stu-id="36e82-110">If the row count fails, the checksum is not performed.</span></span>  
  
 <span data-ttu-id="36e82-111">**Arrêter l'Agent de distribution une fois la validation terminée**</span><span class="sxs-lookup"><span data-stu-id="36e82-111">**Stop the Distribution Agent after the validation has completed**</span></span>  
 <span data-ttu-id="36e82-112">Par défaut, l'Agent de distribution s'exécute en permanence.</span><span class="sxs-lookup"><span data-stu-id="36e82-112">By default, the Distribution Agent runs continuously.</span></span> <span data-ttu-id="36e82-113">Sélectionnez cette option pour arrêter l'agent lorsque la validation est terminée.</span><span class="sxs-lookup"><span data-stu-id="36e82-113">Select this option to stop the agent after validation is performed.</span></span> <span data-ttu-id="36e82-114">Cela permet de vérifier que la validation a réussi avant de continuer à répliquer des données vers l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="36e82-114">This allows you to check whether validation was successful before continuing to replicate data to the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36e82-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="36e82-115">See Also</span></span>  
 <span data-ttu-id="36e82-116">[Valider les données sur l’abonné](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="36e82-116">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="36e82-117">Valider des données répliquées</span><span class="sxs-lookup"><span data-stu-id="36e82-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
