---
title: Options des attributs fixes et variables (Assistant Dimension à variation lente) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.attriboption.f1
ms.assetid: c841345c-7d03-452f-9379-1c8c464f029c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df654cd97b343179828ebd94dea40eacc90e003d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602226"
---
# <a name="fixed-and-changing-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="04db9-102">Options des attributs fixes et variables (Assistant Dimension à variation lente)</span><span class="sxs-lookup"><span data-stu-id="04db9-102">Fixed and Changing Attribute Options (Slowly Changing Dimension Wizard</span></span>
  <span data-ttu-id="04db9-103">Utilisez la boîte de dialogue **Options des attributs fixes et variables** pour spécifier comment répondre aux modifications apportées aux attributs fixes et variables.</span><span class="sxs-lookup"><span data-stu-id="04db9-103">Use the **Fixed and Changing Attribute Options** dialog box to specify how to respond to changes in fixed and changing attributes.</span></span>  
  
 <span data-ttu-id="04db9-104">Pour en savoir plus sur cet Assistant, consultez [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="04db9-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="04db9-105">Options</span><span class="sxs-lookup"><span data-stu-id="04db9-105">Options</span></span>  
 <span data-ttu-id="04db9-106">**Attributs fixes**</span><span class="sxs-lookup"><span data-stu-id="04db9-106">**Fixed attributes**</span></span>  
 <span data-ttu-id="04db9-107">Pour les attributs fixes, indiquez si la tâche doit échouer lorsqu'un changement est détecté dans un attribut fixe.</span><span class="sxs-lookup"><span data-stu-id="04db9-107">For fixed attributes, indicate whether the task should fail if a change is detected in a fixed attribute.</span></span>  
  
 <span data-ttu-id="04db9-108">**Modification des attributs**</span><span class="sxs-lookup"><span data-stu-id="04db9-108">**Changing attributes**</span></span>  
 <span data-ttu-id="04db9-109">Pour les attributs variables, spécifiez si la tâche doit modifier les enregistrements obsolètes ou expirés, en plus des enregistrements actuels, lorsqu'un changement est détecté dans un attribut variable.</span><span class="sxs-lookup"><span data-stu-id="04db9-109">For changing attributes, indicate whether the task should change outdated or expired records, in addition to current records, when a change is detected in a changing attribute.</span></span> <span data-ttu-id="04db9-110">Un enregistrement expiré est un enregistrement qui a été remplacé par un enregistrement plus récent par une modification d'un attribut d'historique (modification de Type 2).</span><span class="sxs-lookup"><span data-stu-id="04db9-110">An expired record is a record that has been replaced with a newer record by a change in a historical attribute (a Type 2 change).</span></span> <span data-ttu-id="04db9-111">La sélection de cette option peut imposer des exigences de traitement supplémentaires sur un objet multidimensionnel construit sur l'entrepôt de données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="04db9-111">Selecting this option may impose additional processing requirements on a multidimensional object constructed on the relational data warehouse.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04db9-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="04db9-112">See Also</span></span>  
 [<span data-ttu-id="04db9-113">Configurer les sorties à l'aide de l'Assistant Dimension à variation lente</span><span class="sxs-lookup"><span data-stu-id="04db9-113">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
