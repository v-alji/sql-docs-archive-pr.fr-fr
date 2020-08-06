---
title: Extension de la fonctionnalité OLAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 49a17ff3-94e9-4969-84fc-37d49e63933b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d64d1ac46e2571aa6f8065a8ea42e4cc43aa589e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614857"
---
# <a name="extending-olap-functionality"></a><span data-ttu-id="0af79-102">Étendre les fonctionnalités OLAP</span><span class="sxs-lookup"><span data-stu-id="0af79-102">Extending OLAP functionality</span></span>
  <span data-ttu-id="0af79-103">En tant que programmeur, vous pouvez étendre Analysis Services en entrant des assemblys, des extensions personnalisées et des procédures stockées pour fournir les fonctionnalités que vous souhaitez utiliser et rediriger dans plusieurs applications de base de données.</span><span class="sxs-lookup"><span data-stu-id="0af79-103">As a programmer, you can extend Analysis Services by writing assemblies, personalized extensions, and stored procedures that provide functionality you want to use and repurpose in multiple database applications.</span></span> <span data-ttu-id="0af79-104">Les assemblys sont utilisés pour étendre les fonctionnalités de modèles multidimensionnels en ajoutant de nouvelles procédures et fonctions au langage MDX ou au moyen du complément de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="0af79-104">Assemblies are used to extend multidimensional models functionality by adding new procedures and functions to the MDX language or by means of the personalization addin.</span></span>  
  
 <span data-ttu-id="0af79-105">Les procédures stockées peuvent être utilisées pour appeler des routines externes, ce qui simplifie le développement et l'implémentation de la base de données Analysis Services grâce au développement d'un code commun qui est stocké dans un seul emplacement.</span><span class="sxs-lookup"><span data-stu-id="0af79-105">Stored procedures can be used to call external routines, simplifying Analysis Services database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="0af79-106">Les procédures stockées peuvent être utilisées pour ajouter à vos applications des fonctionnalités métier qui ne sont pas fournies par les fonctionnalités natives de MDX.</span><span class="sxs-lookup"><span data-stu-id="0af79-106">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="0af79-107">Les personnalisations sont des objets personnalisés que vous ajoutez à un cube pour fournir un comportement qui varie selon l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0af79-107">Personalizations are custom objects that you add to a cube to provide a behavior that varies by user.</span></span> <span data-ttu-id="0af79-108">Les personnalisations ne sont pas des objets permanents dans le cube. Il s'agit d'objets que l'application cliente applique dynamiquement pendant la session de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0af79-108">Personalizations are not permanent objects in the cube, but are objects that the client application applies dynamically during the user's session.</span></span> <span data-ttu-id="0af79-109">Voici quelques exemples : modifier la devise d'une valeur monétaire en fonction de la personne qui accède aux données en fournissant des indicateurs de performance clés individualisés, ou créer une liste ciblée de suggestions pour les clients standard qui achètent en ligne.</span><span class="sxs-lookup"><span data-stu-id="0af79-109">Examples include changing the currency of a monetary value depending on the person accessing the data, providing individualized KPIs, or a targeted suggestion list for regular customers who purchase online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0af79-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0af79-110">In This Section</span></span>  
 [<span data-ttu-id="0af79-111">Extension d'OLAP par des personnalisations</span><span class="sxs-lookup"><span data-stu-id="0af79-111">Extending OLAP through personalizations</span></span>](extending-olap-through-personalizations.md)  
  
 [<span data-ttu-id="0af79-112">Extensions de personnalisation Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0af79-112">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
 [<span data-ttu-id="0af79-113">Définition de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="0af79-113">Defining Stored Procedures</span></span>](../../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
