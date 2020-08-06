---
title: Se connecter au serveur (Oracle), Propriétés de connexion | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.connectionprops.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 1bb7396f-cbb2-4f88-b82b-543287ed4172
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c76a3058283a098357701a44de48efff917acd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600825"
---
# <a name="connect-to-server-oracle-connection-properties"></a><span data-ttu-id="60490-102">Se connecter au serveur (Oracle), Propriétés de connexion</span><span class="sxs-lookup"><span data-stu-id="60490-102">Connect to Server (Oracle), Connection Properties</span></span>
  <span data-ttu-id="60490-103">L'onglet **Propriétés de connexion** de la boîte de dialogue **Se connecter au serveur** permet de spécifier une option de publication **Passerelle** ou **Complet**.</span><span class="sxs-lookup"><span data-stu-id="60490-103">Use the **Connection Properties** tab of the **Connect to Server** dialog box to specify a publishing option of **Gateway** or **Complete**.</span></span> <span data-ttu-id="60490-104">Une fois qu'un serveur de publication est identifié, vous ne pouvez pas modifier cette option sans supprimer et reconfigurer ce serveur.</span><span class="sxs-lookup"><span data-stu-id="60490-104">After a Publisher is identified, this option cannot be changed without dropping and reconfiguring the Publisher.</span></span> <span data-ttu-id="60490-105">Pour plus d’informations, consultez [Configurer un serveur de publication Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="60490-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="60490-106">Options</span><span class="sxs-lookup"><span data-stu-id="60490-106">Options</span></span>  
 <span data-ttu-id="60490-107">**Type d’éditeur**</span><span class="sxs-lookup"><span data-stu-id="60490-107">**Publisher type**</span></span>  
 <span data-ttu-id="60490-108">Sélectionnez **Passerelle** ou **Complet**.</span><span class="sxs-lookup"><span data-stu-id="60490-108">Select **Gateway** or **Complete**.</span></span> <span data-ttu-id="60490-109">L'option **Complet** a pour but de fournir un instantané et des publications transactionnelles avec le jeu complet de fonctionnalités prises en charge pour le serveur de publication Oracle.</span><span class="sxs-lookup"><span data-stu-id="60490-109">The **Complete** option is designed to provide snapshot and transactional publications with the complete set of supported features for Oracle publishing.</span></span> <span data-ttu-id="60490-110">L'option **Passerelle** permet l'optimisation de la conception en améliorant les performances pour les cas où la réplication sert de passerelle entre les systèmes.</span><span class="sxs-lookup"><span data-stu-id="60490-110">The **Gateway** option provides specific design optimizations to improve performance for cases where replication serves as a gateway between systems.</span></span> <span data-ttu-id="60490-111">Vous ne pouvez pas utiliser l'option **Passerelle** si vous envisagez de publier la même table dans plusieurs publications transactionnelles.</span><span class="sxs-lookup"><span data-stu-id="60490-111">The **Gateway** option cannot be used if you plan to publish the same table in multiple transactional publications.</span></span> <span data-ttu-id="60490-112">Une table peut apparaître au maximum dans une publication transactionnelle et dans une ou plusieurs publications d'instantané si vous sélectionnez **Passerelle**.</span><span class="sxs-lookup"><span data-stu-id="60490-112">A table can appear in at most one transactional publication and any number of snapshot publications if you select **Gateway**.</span></span>  
  
 <span data-ttu-id="60490-113">**Délais d'attente**</span><span class="sxs-lookup"><span data-stu-id="60490-113">**Timeouts**</span></span>  
 <span data-ttu-id="60490-114">Indiquez la durée pendant laquelle le serveur de distribution [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit essayer de se connecter au serveur de publication Oracle avant qu’une erreur d’expiration de délai ne se produise.</span><span class="sxs-lookup"><span data-stu-id="60490-114">Specify how long the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor should attempt to connect to the Oracle Publisher before a timeout error occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60490-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60490-115">See Also</span></span>  
 <span data-ttu-id="60490-116">[Glossaire des termes de la publication Oracle](non-sql/glossary-of-terms-for-oracle-publishing.md) </span><span class="sxs-lookup"><span data-stu-id="60490-116">[Glossary of Terms for Oracle Publishing](non-sql/glossary-of-terms-for-oracle-publishing.md) </span></span>  
 [<span data-ttu-id="60490-117">Réglage des performances pour les serveurs de publication Oracle</span><span class="sxs-lookup"><span data-stu-id="60490-117">Performance Tuning for Oracle Publishers</span></span>](non-sql/performance-tuning-for-oracle-publishers.md)  
  
  
