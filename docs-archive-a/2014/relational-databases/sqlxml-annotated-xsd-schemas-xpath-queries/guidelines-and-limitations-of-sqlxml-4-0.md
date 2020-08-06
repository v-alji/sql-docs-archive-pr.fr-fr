---
title: Instructions et limitations de SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
ms.assetid: fe433d30-90a1-421e-85c6-af13294dc18d
author: rothja
ms.author: jroth
ms.openlocfilehash: e020cbf0ac32e4c878b0b74b67e7c9c679d5d178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599863"
---
# <a name="guidelines-and-limitations-of-sqlxml-40"></a><span data-ttu-id="2183e-102">Recommandations et limitations de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="2183e-102">Guidelines and Limitations of SQLXML 4.0</span></span>
  <span data-ttu-id="2183e-103">Gardez en mémoire les points suivants lors de l'utilisation de SQLXML 4.0 :</span><span class="sxs-lookup"><span data-stu-id="2183e-103">Remember the following when working with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="2183e-104">Le XML retourné en tant que résultat de requête n'est pas validé par rapport au schéma de mappage qui a généré le XML.</span><span class="sxs-lookup"><span data-stu-id="2183e-104">XML returned as a query result is not validated against the mapping schema that generated the XML.</span></span>  
  
-   <span data-ttu-id="2183e-105">SQLXML 4.0 inclut des PROGID dépendants et indépendants de la version.</span><span class="sxs-lookup"><span data-stu-id="2183e-105">SQLXML 4.0 includes version-independent and version-dependent PROGIDs.</span></span> <span data-ttu-id="2183e-106">Il est recommandé que toutes les applications de production utilisent des PROGID dépendants de la version.</span><span class="sxs-lookup"><span data-stu-id="2183e-106">It is recommended that all production applications use version-dependent PROGIDs.</span></span> <span data-ttu-id="2183e-107">Ceci est tout particulièrement important car SQLXML 4.0 n'a pas une compatibilité descendante complète.</span><span class="sxs-lookup"><span data-stu-id="2183e-107">This is especially important because SQLXML 4.0 is not fully backward compatible.</span></span> <span data-ttu-id="2183e-108">L'utilisation de PROGID dépendant de la version offre une protection contre les échecs de production éventuels lors de l'installation de versions plus récentes.</span><span class="sxs-lookup"><span data-stu-id="2183e-108">Using version dependent PROGIDs protects from possible production failures when you install newer releases.</span></span> <span data-ttu-id="2183e-109">De version en version, le comportement du programme peut changer pour de multiples raisons comme la résolution de bogues, les modifications de conception, etc.</span><span class="sxs-lookup"><span data-stu-id="2183e-109">From release to release, program behavior may change for a variety of reasons, such as bug fixes, possible design changes, and so on.</span></span> <span data-ttu-id="2183e-110">L'utilisation de PROGID dépendants de la version offre une protection contre les échecs inattendus de l'installation de versions plus récentes.</span><span class="sxs-lookup"><span data-stu-id="2183e-110">Using version-dependent PROGIDs protects from unexpected failure when you install newer releases.</span></span> <span data-ttu-id="2183e-111">Avec des PROGID dépendants de la version, lorsque vous installez une version plus récente, votre application continuera de fonctionner sans échec.</span><span class="sxs-lookup"><span data-stu-id="2183e-111">With version-dependent PROGIDs, when you install a newer release, your application will continue to work without failure.</span></span> <span data-ttu-id="2183e-112">Si vous décidez de modifier les précédents PROGID dépendants de la version pour en utiliser de plus récents dans une nouvelle version, vous devez tester votre application avant de la mettre en production.</span><span class="sxs-lookup"><span data-stu-id="2183e-112">If you decide to change the previous version-dependent PROGIDs and use the recent version-dependent PROGIDs in a newer release, you must test your application before putting it into production.</span></span> <span data-ttu-id="2183e-113">Par exemple, les applications qui utilisent des PROGID indépendants de la version peuvent échouer dans le scénario suivant :</span><span class="sxs-lookup"><span data-stu-id="2183e-113">For example, applications using version-independent PROGIDs may fail in the following scenario:</span></span>  
  
     <span data-ttu-id="2183e-114">Vous exécutez une application qui utilise SQLXML 4.0 et des PROGID indépendants de la version, et vous décidez d'installer un autre programme.</span><span class="sxs-lookup"><span data-stu-id="2183e-114">You are running an application that uses SQLXML 4.0 and version-independent PROGIDs, and you decide to install some other software program.</span></span> <span data-ttu-id="2183e-115">Ce programme peut installer une version antérieure de SQLXML.</span><span class="sxs-lookup"><span data-stu-id="2183e-115">This program might install an earlier version of SQLXML.</span></span> <span data-ttu-id="2183e-116">Votre application risque d'échouer car les PROGID indépendants de la version de votre application pointent maintenant vers la version antérieure de SQLXML, qui peut ou non avoir la fonctionnalité SQLXML utilisée par votre application.</span><span class="sxs-lookup"><span data-stu-id="2183e-116">Your application may fail because the version-independent PROGIDS in your application now point to the earlier version of SQLXML, which may or may not have the SQLXML feature that your application is using.</span></span>  
  
-   <span data-ttu-id="2183e-117">Si, pour une raison quelconque, vous ne souhaitez pas utiliser le fournisseur SQLXMLOLEDB et que vous souhaitez plutôt utiliser le fournisseur SQLOLEDB pour les fonctionnalités SQLXML, définissez la propriété **SQLXML Version** sur « SQLXML. 4.0 ».</span><span class="sxs-lookup"><span data-stu-id="2183e-117">If for any reason you don't want to use the SQLXMLOLEDB provider, and instead want to use the SQLOLEDB provider for SQLXML features, set the **SQLXML Version** property to "SQLXML.4.0".</span></span>  
  
  
