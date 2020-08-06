---
title: Propriétés du serveur (page Paramètres divers du serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.miscserversettings.f1
ms.assetid: b170c066-30cd-42dd-8d34-aa129ea09551
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a82a787140141c3bfa7b18776328a813be9f41f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610850"
---
# <a name="server-properties-misc-server-settings-page"></a><span data-ttu-id="ca858-102">Propriétés du serveur (page Paramètres divers du serveur)</span><span class="sxs-lookup"><span data-stu-id="ca858-102">Server Properties (Misc Server Settings Page)</span></span>
  <span data-ttu-id="ca858-103">Utilisez cette page pour afficher ou modifier les paramètres du serveur.</span><span class="sxs-lookup"><span data-stu-id="ca858-103">Use this page to view or modify your server settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ca858-104">Options</span><span class="sxs-lookup"><span data-stu-id="ca858-104">Options</span></span>  
 <span data-ttu-id="ca858-105">**Langue par défaut pour l'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ca858-105">**Default language for users**</span></span>  
 <span data-ttu-id="ca858-106">Spécifie la langue par défaut de toutes les nouvelles connexions.</span><span class="sxs-lookup"><span data-stu-id="ca858-106">Specifies the default language for all newly created logins.</span></span>  
  
 <span data-ttu-id="ca858-107">**Autoriser les déclencheurs à déclencher d'autres déclencheurs**</span><span class="sxs-lookup"><span data-stu-id="ca858-107">**Allow triggers to fire other triggers**</span></span>  
 <span data-ttu-id="ca858-108">Détermine si un déclencheur peut exécuter une action qui démarre un autre déclencheur.</span><span class="sxs-lookup"><span data-stu-id="ca858-108">Controls whether a trigger can perform an action that initiates another trigger.</span></span> <span data-ttu-id="ca858-109">Lorsque cette option est désactivée, les déclencheurs ne peuvent pas être déclenchés par un autre.</span><span class="sxs-lookup"><span data-stu-id="ca858-109">When cleared, triggers cannot be fired by another trigger.</span></span> <span data-ttu-id="ca858-110">Lorsque cette option est activée, des déclencheurs peuvent être déclenchés par d'autres, jusqu'à 32 niveaux maximum.</span><span class="sxs-lookup"><span data-stu-id="ca858-110">When selected, triggers can be fired by other triggers to as many as 32 levels.</span></span>  
  
 <span data-ttu-id="ca858-111">**Utiliser l'Administrateur de requêtes pour empêcher les requêtes longues**</span><span class="sxs-lookup"><span data-stu-id="ca858-111">**Use query governor to prevent long-running queries**</span></span>  
 <span data-ttu-id="ca858-112">Spécifie une limite supérieure de durée d'exécution d'une requête.</span><span class="sxs-lookup"><span data-stu-id="ca858-112">Specifies an upper limit on the time within which a query can run.</span></span> <span data-ttu-id="ca858-113">Le coût d'une requête correspond à la durée estimée (en secondes) nécessaire à l'exécution d'une requête dans une configuration matérielle donnée.</span><span class="sxs-lookup"><span data-stu-id="ca858-113">Query cost refers to the estimated elapsed time, in seconds, required to execute a query on a specific hardware configuration.</span></span> <span data-ttu-id="ca858-114">Par défaut, l'Administrateur de requêtes est désactivé et toutes les requêtes peuvent être exécutées.</span><span class="sxs-lookup"><span data-stu-id="ca858-114">By default, the query governor is turned off and all queries are allowed to run.</span></span> <span data-ttu-id="ca858-115">Si cette option est activée, vous devez entrer une limite de durée dans la zone de texte qui suit.</span><span class="sxs-lookup"><span data-stu-id="ca858-115">If this option is selected, you must enter a time limit in the text box below.</span></span> <span data-ttu-id="ca858-116">Si vous spécifiez une valeur positive et différente de zéro, l'Administrateur de requêtes n'autorise pas l'exécution de requêtes dont le coût estimé excède cette valeur.</span><span class="sxs-lookup"><span data-stu-id="ca858-116">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost exceeding that value.</span></span>  
  
 <span data-ttu-id="ca858-117">**Interpréter une année sur deux chiffres comme comprise entre**</span><span class="sxs-lookup"><span data-stu-id="ca858-117">**Interpret a two-digit year as falling between**</span></span>  
 <span data-ttu-id="ca858-118">Spécifie la plage de dates de 100 ans pour interpréter les valeurs d'année à deux chiffres.</span><span class="sxs-lookup"><span data-stu-id="ca858-118">Specifies the 100-year date range for interpreting two-digit year values.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ca858-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interprétera les valeurs de date à deux chiffres pour faire référence à l’année se terminant par ces chiffres figurant dans la plage spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ca858-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will interpret two-digit date values to refer to the year ending in those digits that falls within the specified range.</span></span>  
  
 <span data-ttu-id="ca858-120">Spécifiez la dernière année dans la zone de droite.</span><span class="sxs-lookup"><span data-stu-id="ca858-120">Set the right box with the ending year.</span></span> <span data-ttu-id="ca858-121">Lorsque la dernière année est enregistrée, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] remplit automatiquement la zone de gauche avec la première année.</span><span class="sxs-lookup"><span data-stu-id="ca858-121">When the ending year is saved, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will automatically populate the left box with the beginning year.</span></span>  
  
 <span data-ttu-id="ca858-122">**Valeurs configurées**</span><span class="sxs-lookup"><span data-stu-id="ca858-122">**Configured Values**</span></span>  
 <span data-ttu-id="ca858-123">Affiche les valeurs configurées pour les options de ce volet.</span><span class="sxs-lookup"><span data-stu-id="ca858-123">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="ca858-124">Si vous modifiez ces valeurs, cliquez sur **Valeurs en cours d’exécution** pour vérifier si les modifications ont été prises en compte.</span><span class="sxs-lookup"><span data-stu-id="ca858-124">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="ca858-125">Si ce n'est pas le cas, vous devez redémarrer l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca858-125">If the changes have not taken effect, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restated first.</span></span>  
  
 <span data-ttu-id="ca858-126">**Valeurs en cours d’exécution**</span><span class="sxs-lookup"><span data-stu-id="ca858-126">**Running Values**</span></span>  
 <span data-ttu-id="ca858-127">Affiche les valeurs en cours d'exécution pour les options de ce volet.</span><span class="sxs-lookup"><span data-stu-id="ca858-127">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="ca858-128">Ces valeurs sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="ca858-128">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca858-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca858-129">See Also</span></span>  
 [<span data-ttu-id="ca858-130">Options de configuration de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca858-130">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
