---
title: Serveurs de publication | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.enablepublishers.f1
ms.assetid: 116cd6a5-32ac-4273-81a2-d184408e0f07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 879fa3cc2ecadf56914928c6ae83600f513f6ddb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599886"
---
# <a name="publishers"></a><span data-ttu-id="738b8-102">Serveurs de publication</span><span class="sxs-lookup"><span data-stu-id="738b8-102">Publishers</span></span>
  <span data-ttu-id="738b8-103">Vous pouvez autoriser les autres serveurs de publication à utiliser ce serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="738b8-103">You can give permission for other Publishers to use this Distributor.</span></span> <span data-ttu-id="738b8-104">Notez que l'activation d'un serveur de publication pour utiliser ce serveur en tant que serveur de distribution distant ne fait pas de ce serveur un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="738b8-104">Be aware that enabling a Publisher to use this server as its remote Distributor does not make that server a Publisher.</span></span> <span data-ttu-id="738b8-105">Vous devez vous connecter au serveur de publication, le configurer pour la publication, et choisir ce serveur comme distributeur.</span><span class="sxs-lookup"><span data-stu-id="738b8-105">You must connect to the Publisher, configure it for publishing, and choose this server as the Distributor.</span></span> <span data-ttu-id="738b8-106">Vous pouvez configurer le serveur de publication et choisir un serveur de distribution à l'aide de l'Assistant Nouvelle publication.</span><span class="sxs-lookup"><span data-stu-id="738b8-106">You can configure the Publisher and choose a Distributor through the New Publication Wizard.</span></span>  
  
 <span data-ttu-id="738b8-107">Les serveurs, que vous sélectionnez en tant que serveurs de publication, utilisent la base de données de distribution spécifiée dans la page **Base de données de distribution** de cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="738b8-107">The servers you select as Publishers will use the distribution database specified on the **Distribution Database** page of this wizard.</span></span> <span data-ttu-id="738b8-108">Si vous souhaitez utiliser une autre base de données de distribution, n'activez pas le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="738b8-108">If you want to use a different distribution database, do not enable the Publisher at this time.</span></span> <span data-ttu-id="738b8-109">Utilisez plutôt la boîte de dialogue **Propriétés du serveur de distribution** pour ajouter des serveurs de publication après avoir terminé l'exécution de l'Assistant Configuration de la distribution.</span><span class="sxs-lookup"><span data-stu-id="738b8-109">Instead, use the **Distributor Properties** dialog box to add Publishers after you complete the Configure Distribution Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="738b8-110">Options</span><span class="sxs-lookup"><span data-stu-id="738b8-110">Options</span></span>  
 <span data-ttu-id="738b8-111">**Serveurs de publication**</span><span class="sxs-lookup"><span data-stu-id="738b8-111">**Publishers**</span></span>  
 <span data-ttu-id="738b8-112">Sélectionnez les serveurs autorisés à utiliser ce serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="738b8-112">Select the servers that are allowed to use this Distributor.</span></span> <span data-ttu-id="738b8-113">Cliquez sur le bouton des propriétés ( **...** ) en regard d'un serveur de publication pour afficher et définir des propriétés supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="738b8-113">Click the properties button (**...**) next to a Publisher to view and set additional properties.</span></span>  
  
 <span data-ttu-id="738b8-114">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="738b8-114">**Add**</span></span>  
 <span data-ttu-id="738b8-115">Si le serveur souhaité ne figure pas dans la liste, cliquez sur **Ajouter** afin d'ajouter un serveur de publication [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou un serveur de publication Oracle à la liste des serveurs de publication disponibles.</span><span class="sxs-lookup"><span data-stu-id="738b8-115">If the server you want to allow is not listed, click **Add** to add a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher or Oracle Publisher to the list of available Publishers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738b8-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="738b8-116">See Also</span></span>  
 <span data-ttu-id="738b8-117">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="738b8-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="738b8-118">[Configurer la publication et la distribution](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="738b8-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="738b8-119">[Afficher et modifier les propriétés d’un serveur de distribution et d’un serveur de publication](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="738b8-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="738b8-120">Créer une publication</span><span class="sxs-lookup"><span data-stu-id="738b8-120">Create a Publication</span></span>](publish/create-a-publication.md)  
  
  
