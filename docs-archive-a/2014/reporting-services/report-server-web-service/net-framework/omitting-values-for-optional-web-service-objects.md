---
title: Omission de valeurs pour les objets de service web facultatifs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], omitted values
- XML Web service [Reporting Services], omitted values
- Report Server Web service, omitted values
- omitting values [Reporting Services]
ms.assetid: ceb68b8b-9214-4745-abc9-f47f33ecd6f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3858f73e1b332acfa1a1bbc640007f6f0884abff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697495"
---
# <a name="omitting-values-for-optional-web-service-objects"></a><span data-ttu-id="e93f8-102">Omission de valeurs pour les objets de service Web facultatifs</span><span class="sxs-lookup"><span data-stu-id="e93f8-102">Omitting Values for Optional Web Service Objects</span></span>
  <span data-ttu-id="e93f8-103">Les propriétés de plusieurs des types complexes du services web Report Server sont souvent suivies d’une propriété appelée Specified.</span><span class="sxs-lookup"><span data-stu-id="e93f8-103">Properties of several of the Report Server Web service complex types have an accompanying property known as the Specified property.</span></span> <span data-ttu-id="e93f8-104">Lorsque c'est le cas, le nom des propriétés se compose de leur nom original suivi de la mention « Specified ».</span><span class="sxs-lookup"><span data-stu-id="e93f8-104">The name of the property consists of the original property name with the word "Specified" appended to it.</span></span> <span data-ttu-id="e93f8-105">La présence de cette mention signifie que certaines valeurs des propriétés peuvent parfois être omises.</span><span class="sxs-lookup"><span data-stu-id="e93f8-105">The presence of this property indicates that a value for the original property may sometimes be omitted.</span></span> <span data-ttu-id="e93f8-106">Ce phénomène est la conséquence directe de la conversion à partir du langage WSDL (Web Service Description Language) dans une classe proxy du [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e93f8-106">This is a direct result of the translation from the Web Service Description Language (WSDL) to a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class.</span></span> <span data-ttu-id="e93f8-107">Par exemple, la propriété de service Web <xref:ReportService2010.DataSourceDefinition.Enabled%2A> de type complexe <xref:ReportService2010.DataSourceDefinition> est suivie d'une propriété intitulée <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span><span class="sxs-lookup"><span data-stu-id="e93f8-107">For example, the Web service property <xref:ReportService2010.DataSourceDefinition.Enabled%2A> of the complex type <xref:ReportService2010.DataSourceDefinition> has an accompanying property named <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span></span> <span data-ttu-id="e93f8-108">Lorsque vous développez une application et que vous ne souhaitez pas définir de valeur pour la propriété <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, vous n'avez pas à attribuer de valeur à <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, la valeur par défaut `true` étant en effet utilisée.</span><span class="sxs-lookup"><span data-stu-id="e93f8-108">If you are building an application and do not want to set a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you do not have to supply a value for <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; the default value of `true` is used.</span></span> <span data-ttu-id="e93f8-109">Toutefois, pour que cette opération se vérifie, vous devez au préalable définir <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> sur `false`.</span><span class="sxs-lookup"><span data-stu-id="e93f8-109">However, you still need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> to `false`.</span></span> <span data-ttu-id="e93f8-110">Lorsque vous attribuez une valeur à la propriété <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, vous devez définir <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> sur `true`.</span><span class="sxs-lookup"><span data-stu-id="e93f8-110">If you supply a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> equal to `true`.</span></span> <span data-ttu-id="e93f8-111">Seules les propriétés accessibles en écriture nécessitent de respecter cette condition.</span><span class="sxs-lookup"><span data-stu-id="e93f8-111">This is the case for writable properties.</span></span> <span data-ttu-id="e93f8-112">En revanche, les propriétés en lecture seule ne requièrent aucune action de votre part.</span><span class="sxs-lookup"><span data-stu-id="e93f8-112">For read-only properties, you do not need to take any action.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e93f8-113">Si vous ne parvenez pas à spécifier une propriété en suivant la procédure mentionnée ci-avant, le comportement du service Web peut se révéler imprévisible.</span><span class="sxs-lookup"><span data-stu-id="e93f8-113">Failure to specify a property using the above-mentioned technique can result in unpredictable Web service behavior.</span></span>  
  
 <span data-ttu-id="e93f8-114">Les types de données qui requièrent généralement la gestion de la propriété spécifiée supplémentaire sont `Boolean` , `DateTime` et `Enumeration` .</span><span class="sxs-lookup"><span data-stu-id="e93f8-114">The data types that usually require you to handle the additional Specified property are `Boolean`, `DateTime`, and `Enumeration`.</span></span>  
  
 <span data-ttu-id="e93f8-115">Pour obtenir un exemple, consultez la méthode <xref:ReportService2010.ReportingService2010.CreateDataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="e93f8-115">For an example, see <xref:ReportService2010.ReportingService2010.CreateDataSource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93f8-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e93f8-116">See Also</span></span>  
 <span data-ttu-id="e93f8-117">[Création d’applications à l’aide du service web et du .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="e93f8-117">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="e93f8-118">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e93f8-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
