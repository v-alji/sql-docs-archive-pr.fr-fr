---
title: Magasin d’objets BLOB distants (RBS) et groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 01a70258-d4fd-40bc-bc44-c490b5d6c420
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12a11162d286731b2b510a9051183e6c3025b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603057"
---
# <a name="remote-blob-store-rbs-and-alwayson-availability-groups-sql-server"></a>Magasin d'objets blob distants et groupes de disponibilité AlwaysOn (SQL Server)
  [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]peut fournir une solution de haute disponibilité et de récupération d’urgence pour les [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] objets BLOB du magasin d’objets [BLOB distants (RBS](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) ). [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] protège les métadonnées et schémas du magasin d’objets blob distants stockés dans une base de données de disponibilité en les répliquant sur des réplicas secondaires. Il s'agit de la base de données de contenu SharePoint. De manière générale, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stocke ces métadonnées RBS indépendamment de l'objet blob.  
  
 La protection des données BLOB de RBD dépend de l'emplacement du magasin d'objets BLOB, comme suit :  
  
|Emplacement du magasin d'objets BLOB|Les groupes de disponibilité peuvent-ils protéger ces données BLOB ?|  
|-------------------------|-----------------------------------------------------|  
|La même base de données qui contient les métadonnées du magasin d'objets blob distants (stockées à l'aide d'un fournisseur FILESTREAM distant de RBS)|Oui|  
|Une autre base de données dans la même instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (enregistrée à l'aide d'un fournisseur FILESTREAM distant de RBS)|Oui<br /><br /> Nous vous recommandons de placer cette base de données dans le même groupe de disponibilité que la base de données qui contient les métadonnées du magasin d'objets blob distants.|  
|Une autre base de données dans une autre instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (enregistrée à l'aide d'un fournisseur FILESTREAM distant de RBS)|Oui<br /><br /> Cette base de données doit être dans un groupe de disponibilité distinct.|  
|Un magasin d'objets BLOB tiers|Non<br /><br /> Pour protéger ces données BLOB, utilisez les mécanismes de haute disponibilité du fournisseur de magasin d'objets blob.|  
  
##  <a name="limitations"></a><a name="Limitations"></a> Limitations  
  
-   Les chargés de maintenance RBS doivent être ciblés sur le réplica principal.  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> Recommandations  
  
-   Utilisez un écouteur de groupe de disponibilité. Pour plus d’informations, consultez [Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> Contenu associé  
  
-   [Maintenance du magasin d’objets BLOB distants](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (dans la documentation en ligne de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] )  
  
-   [Running RBS Maintainer (Exécution du chargé de maintenance RBS)](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)  
  
-   [Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010) (Configurer le stockage d’objets blob distants avec le fournisseur FILESTREAM)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)  
  
## <a name="see-also"></a>Voir aussi  
 [Connectivité client AlwaysOn &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md)   
 [Magasin d’objets blob distants &#40;RBS&#41; &#40;SQL Server&#41;](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)  
  
  
