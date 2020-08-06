---
title: Architecture de la mise en forme XML côté client et côté serveur (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], XML formatting architecture
- SQLOLEDB provider
- client-side XML formatting
- data providers [SQLXML], XML formatting architecture
- SQLNCLI, XML
- server-side XML formatting
- SQL Server Native Client, XML
- SQLXMLOLEDB Provider, XML formatting architecture
ms.assetid: 52440d9e-89fd-4c15-a008-a1ea99f41387
author: rothja
ms.author: jroth
ms.openlocfilehash: ae1a9c60a7a7966f4eff2a08b4557487f5aec58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611670"
---
# <a name="architecture-of-client-side-and-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="d0244-102">Architecture de la mise en forme XML côté client et côté serveur (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d0244-102">Architecture of Client-side and Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="d0244-103">L'illustration suivante montre l'architecture de la mise en forme XML côté serveur.</span><span class="sxs-lookup"><span data-stu-id="d0244-103">The following illustration shows the architecture of XML formatting on the server side.</span></span>  
  
 <span data-ttu-id="d0244-104">![Architecture de mise en forme XML côté serveur.](../../../database-engine/dev-guide/media/serversidexml.gif "Architecture de mise en forme XML côté serveur.")</span><span class="sxs-lookup"><span data-stu-id="d0244-104">![Architecture of XML formatting on the server side.](../../../database-engine/dev-guide/media/serversidexml.gif "Architecture of XML formatting on the server side.")</span></span>  
  
 <span data-ttu-id="d0244-105">Dans cet exemple, la commande spécifiée sur le client est envoyée au serveur.</span><span class="sxs-lookup"><span data-stu-id="d0244-105">In this example, the command that is specified on the client is sent to the server.</span></span> <span data-ttu-id="d0244-106">Le serveur produit un document XML et le retourne au client.</span><span class="sxs-lookup"><span data-stu-id="d0244-106">The server produces an XML document and returns it to the client.</span></span> <span data-ttu-id="d0244-107">Dans ce cas, le serveur dispose d’une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0244-107">In this case, the server has an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0244-108">Avec la mise en forme XML côté serveur, vous pouvez utiliser le fournisseur SQLXMLOLEDB ou le fournisseur SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="d0244-108">With server-side XML formatting, you can use either the SQLXMLOLEDB provider or the SQLOLEDB provider.</span></span>  <span data-ttu-id="d0244-109">Le fournisseur SQLXMLOLEDB utilise Sqlxml4.dll qui est inclus dans SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="d0244-109">The SQLXMLOLEDB provider uses Sqlxml4.dll, which is included in SQLXML 4.0.</span></span> <span data-ttu-id="d0244-110">Lorsque vous utilisez le fournisseur SQLOLEDB, vous obtenez par défaut les fonctionnalités SQLXML fournies par Sqlxmlx.dll, inclus avec [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows ou Microsoft Data Access Components (MDAC) 2.6 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d0244-110">When you use the SQLOLEDB provider, by default you get the SQLXML functionality provided by Sqlxmlx.dll, which is included with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows or in Microsoft Data Access Components (MDAC) 2.6 or later.</span></span> <span data-ttu-id="d0244-111">Pour utiliser Sqlxml4.dll avec SQLOLEDB, vous devez définir la propriété de version SQLXML sur « SQLXML. 4.0 » sur l’objet de connexion SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="d0244-111">To use Sqlxml4.dll with SQLOLEDB, you must set the SQLXML Version property to "SQLXML.4.0" on the SQLOLEDB Connection object.</span></span> <span data-ttu-id="d0244-112">Quel que soit le cas, le serveur produit le document XML et l'envoie au client.</span><span class="sxs-lookup"><span data-stu-id="d0244-112">In either case, the server produces the XML document and sends it to the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0244-113">Les requêtes et les codes de mise à jour XPath sont analysés sur le client.</span><span class="sxs-lookup"><span data-stu-id="d0244-113">XPath queries and updategrams are parsed on the client.</span></span> <span data-ttu-id="d0244-114">Pour bénéficier des fonctionnalités du modèle ou du code de mise à jour XPath dans SQLXML 4.0, utilisez Sqlxml4.dll.</span><span class="sxs-lookup"><span data-stu-id="d0244-114">To get the XPath template or updategram functionality in SQLXML 4.0, use Sqlxml4.dll.</span></span>  
  
 <span data-ttu-id="d0244-115">L'illustration suivante montre l'architecture de la mise en forme XML côté client.</span><span class="sxs-lookup"><span data-stu-id="d0244-115">The following illustration shows the architecture of XML formatting on the client side.</span></span>  
  
 <span data-ttu-id="d0244-116">![Architecture de mise en forme XML côté client.](../../../database-engine/dev-guide/media/clientsidexml.gif "Architecture de mise en forme XML côté client.")</span><span class="sxs-lookup"><span data-stu-id="d0244-116">![Architecture of XML formatting on the client side.](../../../database-engine/dev-guide/media/clientsidexml.gif "Architecture of XML formatting on the client side.")</span></span>  
  
 <span data-ttu-id="d0244-117">Dans cet exemple, le client utilise le fournisseur SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="d0244-117">In this example, the client uses the SQLXMLOLEDB provider.</span></span> <span data-ttu-id="d0244-118">Dans la chaîne de connexion, la propriété Fournisseur de données doit être définie sur SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="d0244-118">In the connection string, the Data Provider property must be set to SQLOLEDB.</span></span> <span data-ttu-id="d0244-119">(Il s’agit de la seule valeur acceptée dans SQLXML 4,0.) La commande exécutée sur le client est envoyée au serveur.</span><span class="sxs-lookup"><span data-stu-id="d0244-119">(This is the only value accepted in SQLXML 4.0.) The command that is executed on the client is sent to the server.</span></span> <span data-ttu-id="d0244-120">L'ensemble de lignes généré sur le serveur est envoyé au client.</span><span class="sxs-lookup"><span data-stu-id="d0244-120">The rowset that is generated on the server is sent to the client.</span></span> <span data-ttu-id="d0244-121">La mise en forme du document XML de l'ensemble de lignes est effectuée sur le client.</span><span class="sxs-lookup"><span data-stu-id="d0244-121">The formatting of the XML document from the rowset is performed on the client.</span></span>  
  
 <span data-ttu-id="d0244-122">Dans SQLXML 4.0, le fournisseur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) ou le fournisseur SQLOLEDB peut être utilisé en tant que fournisseur de données.</span><span class="sxs-lookup"><span data-stu-id="d0244-122">In SQLXML 4.0, either the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) or the SQLOLEDB provider can be used as the data provider.</span></span> <span data-ttu-id="d0244-123">Vous pouvez éventuellement accéder à n'importe quelle source de données.</span><span class="sxs-lookup"><span data-stu-id="d0244-123">You can potentially access any data source.</span></span> <span data-ttu-id="d0244-124">Tant que la requête retourne un ensemble de lignes unique, la transformation XML peut être appliquée sur le client.</span><span class="sxs-lookup"><span data-stu-id="d0244-124">As long as the query returns a single rowset, the XML transformation can be applied on the client.</span></span>  
  
  
