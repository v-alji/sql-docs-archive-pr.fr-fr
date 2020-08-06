---
title: Configurer l’accès en mémoire ou DirectQuery pour une base de données model tabulaire | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5d439a9-5be1-4145-90e8-90777d80e98b
author: minewiskan
ms.author: owend
ms.openlocfilehash: a607bc6c11f35736487932bdf10d239afc8b5355
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696200"
---
# <a name="configure-in-memory-or-directquery-access-for-a-tabular-model-database"></a><span data-ttu-id="3263b-102">Configurer l'accès In-Memory ou DirectQuery pour une base de données model tabulaire</span><span class="sxs-lookup"><span data-stu-id="3263b-102">Configure In-Memory or DirectQuery Access for a Tabular Model Database</span></span>
  <span data-ttu-id="3263b-103">Cette rubrique explique comment modifier les propriétés de connexion d'un modèle tabulaire qui a déjà été déployé afin d'activer l'utilisation du modèle en mode de requête directe.</span><span class="sxs-lookup"><span data-stu-id="3263b-103">This topic describes how to change the connection properties of a tabular model that has already been deployed, to enable use of the model in Direct Query mode.</span></span>  
  
 <span data-ttu-id="3263b-104">Pour plus d’informations sur ces propriétés et sur la configuration pour les scénarios les plus courants, consultez [DirectQuery Deployment scenarios &#40;SSAS tabulaire&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="3263b-104">For more information about these properties, and configuration for the most common scenarios, see [DirectQuery Deployment Scenarios &#40;SSAS Tabular&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3263b-105">Spécifications</span><span class="sxs-lookup"><span data-stu-id="3263b-105">Requirements</span></span>  
 <span data-ttu-id="3263b-106">L'activation de l'utilisation du mode de requête directe sur un modèle tabulaire est un processus qui implique plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="3263b-106">Enabling the use of Direct Query mode on a tabular model is a multistep process.</span></span> <span data-ttu-id="3263b-107">Vous devez respecter les consignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3263b-107">You must:</span></span>  
  
1.  <span data-ttu-id="3263b-108">Vérifiez que le modèle n'a pas de fonctionnalités susceptibles de provoquer des erreurs de validation en mode de requête directe.</span><span class="sxs-lookup"><span data-stu-id="3263b-108">Ensure that the model does not have features which might cause validation errors in Direct Query mode.</span></span>  
  
2.  <span data-ttu-id="3263b-109">Modifiez le mode de stockage sur le modèle pour prendre en charge la requête directe.</span><span class="sxs-lookup"><span data-stu-id="3263b-109">Change the storage mode on the model to support Direct Query.</span></span>  
  
3.  <span data-ttu-id="3263b-110">Déployez le modèle dans un mode qui prend en charge les requêtes en mode hybride ou en mode de requête directe pur.</span><span class="sxs-lookup"><span data-stu-id="3263b-110">Deploy the model in a mode that supports queries in either a hybrid or pure Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="3263b-111">Modifiez la chaîne de connexion dans la base de données déployée pour prendre en charge le mode de requête directe.</span><span class="sxs-lookup"><span data-stu-id="3263b-111">Edit the connection string on the deployed database to support Direct Query mode.</span></span>  
  
 <span data-ttu-id="3263b-112">Cette rubrique suppose que vous avez créé et validé votre modèle, et que vous devez uniquement activer l'accès aux requêtes directes à partir d'un client tel que [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3263b-112">This topic assumes that you have created and validated your model, and only need to enable Direct Query access from a client such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="3263b-113">Procédure</span><span class="sxs-lookup"><span data-stu-id="3263b-113">Procedure</span></span>  
  
#### <a name="change-the-connection-string-properties-of-the-model"></a><span data-ttu-id="3263b-114">Modifier les propriétés de chaîne de connexion du modèle</span><span class="sxs-lookup"><span data-stu-id="3263b-114">Change the Connection String Properties of the Model</span></span>  
  
1.  <span data-ttu-id="3263b-115">Dans SQL Server Management Studio, ouvrez l'instance sur laquelle vous avez déployé le modèle.</span><span class="sxs-lookup"><span data-stu-id="3263b-115">In SQL Server Management Studio, open the instance to which you deployed the model.</span></span>  
  
2.  <span data-ttu-id="3263b-116">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nom de la base de données model, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3263b-116">In Object Explorer, right-click the name of the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="3263b-117">Recherchez la propriété **DirectQueryMode**.</span><span class="sxs-lookup"><span data-stu-id="3263b-117">Locate the property, **DirectQueryMode**.</span></span> <span data-ttu-id="3263b-118">Pour activer l'utilisation de la source de données relationnelles, cette propriété doit être définie avec l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3263b-118">To enable use of the relational data source, this property must be set to one of these values:</span></span>  
  
    -   <span data-ttu-id="3263b-119">**DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="3263b-119">**DirectQuery**</span></span>  
  
    -   <span data-ttu-id="3263b-120">**InMemoryWithDirectQuery**</span><span class="sxs-lookup"><span data-stu-id="3263b-120">**InMemoryWithDirectQuery**</span></span>  
  
    -   <span data-ttu-id="3263b-121">**DirectQueryWithInMemory**</span><span class="sxs-lookup"><span data-stu-id="3263b-121">**DirectQueryWithInMemory**</span></span>  
  
  
