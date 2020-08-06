---
title: Implémentation d’une classe DataReader pour une extension pour le traitement des données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], data readers
- data readers [Reporting Services]
- DataReader class
- read-only data
ms.assetid: 23e286e7-6074-4fbe-be29-203420d6c3d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c9e55741c72d624b7149435ced90550135d8b4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708952"
---
# <a name="implementing-a-datareader-class-for-a-data-processing-extension"></a><span data-ttu-id="84aa5-102">Implémentation d'une classe DataReader pour une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="84aa5-102">Implementing a DataReader Class for a Data Processing Extension</span></span>
  <span data-ttu-id="84aa5-103">L’objet **DataReader** permet à un client de récupérer un flux de données avant uniquement et en lecture seule à partir d’une source de données.</span><span class="sxs-lookup"><span data-stu-id="84aa5-103">The **DataReader** object enables a client to retrieve a read-only, forward-only stream of data from a data source.</span></span> <span data-ttu-id="84aa5-104">Les résultats sont retournés à mesure que la requête s’exécute et sont stockés sur le client dans la mémoire tampon réseau jusqu’à ce que vous en fassiez la demande à l’aide de la méthode **Read** de la classe **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="84aa5-104">Results are returned as the query executes and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader** class.</span></span> <span data-ttu-id="84aa5-105">Pour créer une classe **DataReader**, implémentez <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> et, éventuellement, <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span><span class="sxs-lookup"><span data-stu-id="84aa5-105">To create a **DataReader** class, implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> and optionally implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span></span> <span data-ttu-id="84aa5-106">Le fait d’utiliser un objet **DataReader** améliore les performances de l’application : d’une part, les données sont récupérées dès qu’elles sont disponibles (plutôt que d’attendre le retour des résultats complets de la requête) et, d’autre part, une seule ligne à la fois est stockée en mémoire par défaut, réduisant ainsi la charge système.</span><span class="sxs-lookup"><span data-stu-id="84aa5-106">Using a **DataReader** object increases application performance both by retrieving data as soon as it is available, rather than waiting for the entire results of the query to be returned, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="84aa5-107">Après avoir créé une instance de votre classe **Command**, vous créez un objet **DataReader** en appelant **Command.ExecuteReader** pour récupérer des lignes de la source de données.</span><span class="sxs-lookup"><span data-stu-id="84aa5-107">After creating an instance of your **Command** class, you create a **DataReader** object by calling **Command.ExecuteReader** to retrieve rows from the data source.</span></span> <span data-ttu-id="84aa5-108">L’implémentation de **DataReader** doit fournir deux fonctions de base : l’accès avant uniquement sur les jeux de résultats obtenus en exécutant une commande et l’accès aux types, noms et valeurs de colonne dans chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="84aa5-108">The **DataReader** implementation must provide two basic capabilities: forward-only access over the result sets obtained by executing a command and access to the column types, names, and values within each row.</span></span> <span data-ttu-id="84aa5-109">Les clients utilisent la méthode **Read** de l’objet **DataReader** pour obtenir une ligne des résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="84aa5-109">Clients use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span>  
  
 <span data-ttu-id="84aa5-110">Dans le Concepteur de rapports, votre objet **DataReader** est utilisé pour récupérer une liste de champs ainsi que des informations de schéma sur le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="84aa5-110">In Report Designer, your **DataReader** object is used to retrieve a list of fields as well as schema information about the result set.</span></span> <span data-ttu-id="84aa5-111">Pour cela, vous devez implémenter les méthodes **GetName**, **GetValue**, **GetFieldType** et **GetOrdinal** de l’interface <xref:Microsoft.ReportingServices.DataProcessing.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="84aa5-111">This is accomplished by implementing the **GetName**, **GetValue**, **GetFieldType,** and **GetOrdinal** methods of the <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> interface.</span></span>  
  
 <span data-ttu-id="84aa5-112">L'interface <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> vous permet de fournir des informations d'agrégation spécifiques à propos de votre jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="84aa5-112">The <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> interface allows you to supply specific aggregation information about your result set.</span></span> <span data-ttu-id="84aa5-113">Pour un exemple d’implémentation de la classe **DataReader**, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="84aa5-113">For a sample **DataReader** class implementation, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84aa5-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84aa5-114">See Also</span></span>  
 <span data-ttu-id="84aa5-115">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="84aa5-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="84aa5-116">[Implémentation d’une extension pour le traitement des données](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="84aa5-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="84aa5-117">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="84aa5-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
