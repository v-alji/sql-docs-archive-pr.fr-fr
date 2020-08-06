---
title: Propriétés du serveur (page Sécurité) - Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.security.f1
ms.assetid: f49aedc6-f145-4df1-8f69-d5d910f492c6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f709d42bf593b4933d9fc1fdc423c195967df382
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610966"
---
# <a name="server-properties-security-page---reporting-services"></a><span data-ttu-id="24000-102">Propriétés du serveur (page Sécurité) - Reporting Services</span><span class="sxs-lookup"><span data-stu-id="24000-102">Server Properties (Security Page) - Reporting Services</span></span>
  <span data-ttu-id="24000-103">Utilisez cette page pour désactiver des fonctionnalités qui peuvent nuire potentiellement à un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="24000-103">Use this page to turn off features that can potentially compromise a report server.</span></span> <span data-ttu-id="24000-104">La désactivation de ces fonctionnalités limitera certaines d'entre elles, mais peut améliorer la sécurité globale du serveur de rapports en atténuant des menaces spécifiques.</span><span class="sxs-lookup"><span data-stu-id="24000-104">Turning off these features will limit some functionality, but can improve the overall security of the report server by mitigating specific threats.</span></span>  
  
 <span data-ttu-id="24000-105">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à une instance de serveur de rapports, cliquez avec le bouton droit sur le nom du serveur de rapports, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="24000-105">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="24000-106">Cliquez sur **Sécurité** pour ouvrir cette page.</span><span class="sxs-lookup"><span data-stu-id="24000-106">Click **Security** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="24000-107">Options</span><span class="sxs-lookup"><span data-stu-id="24000-107">Options</span></span>  
 <span data-ttu-id="24000-108">**Activer la sécurité intégrée Windows pour les sources de données de rapport**</span><span class="sxs-lookup"><span data-stu-id="24000-108">**Enable Windows integrated security for report data sources**</span></span>  
 <span data-ttu-id="24000-109">Spécifiez si une connexion à une source de données de rapport peut être établie à l'aide du jeton de sécurité Windows de l'utilisateur qui a demandé le rapport.</span><span class="sxs-lookup"><span data-stu-id="24000-109">Specify whether a connection to a report data source can be made using the Windows security token of the user who requested the report.</span></span>  
  
 <span data-ttu-id="24000-110">Si vous désactivez cette fonctionnalité, la fonctionnalité de sécurité intégrée Windows dans les pages de propriétés de la source de données de rapport ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="24000-110">If you turn off this feature, the Windows Integrated Security feature in the report data source property pages will be unavailable.</span></span> <span data-ttu-id="24000-111">Si les sources de données de rapport sont configurées pour la sécurité intégrée Windows et que vous désactivez par la suite cette fonctionnalité, le serveur de rapports mettra immédiatement à jour toutes les propriétés de connexion à la source de données pour demander des informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="24000-111">If report data sources are configured for Windows integrated security and you subsequently turn off this feature, the report server will immediately update all data source connection properties to prompt for credentials.</span></span>  
  
 <span data-ttu-id="24000-112">**Activer la génération d'états ad hoc**</span><span class="sxs-lookup"><span data-stu-id="24000-112">**Enable Ad Hoc Reporting**</span></span>  
 <span data-ttu-id="24000-113">Spécifiez si les utilisateurs peuvent effectuer des requêtes ad hoc à partir d'un rapport du Générateur de rapports, où les nouveaux rapports sont générés automatiquement lorsqu'un utilisateur clique sur des données d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="24000-113">Specify whether users can perform ad hoc queries from a Report Builder report, where new reports are automatically generated when a user clicks data of interest.</span></span>  
  
 <span data-ttu-id="24000-114">La définition de cette option détermine si la propriété `EnableLoadReportDefinition` sur le serveur de rapports a la valeur `True` ou `False`.</span><span class="sxs-lookup"><span data-stu-id="24000-114">Setting this option determines whether the `EnableLoadReportDefinition` property on the report server is set to `True` or `False`.</span></span> <span data-ttu-id="24000-115">Si vous désactivez cette option, la propriété aura la valeur `False` et le serveur de rapports ne générera pas les rapports générés interactifs créés pendant l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="24000-115">If you clear this option, the property will be set to `False` and report server will not generate clickthrough reports that are created during data exploration.</span></span> <span data-ttu-id="24000-116">Tous les appels à la méthode `LoadReportDefinition` seront bloqués.</span><span class="sxs-lookup"><span data-stu-id="24000-116">All calls to the `LoadReportDefinition` method will be blocked.</span></span>  
  
 <span data-ttu-id="24000-117">La désactivation de cette option atténue la menace qu'un utilisateur malveillant lance une attaque par déni de service en surchargeant le serveur de rapports avec des demandes `LoadReportDefinition`.</span><span class="sxs-lookup"><span data-stu-id="24000-117">Turning off this option mitigates a threat whereby a malicious user launches a denial of service attack by overloading the report server with `LoadReportDefinition` requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24000-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24000-118">See Also</span></span>  
 <span data-ttu-id="24000-119">[Définir les propriétés du serveur de rapports &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="24000-119">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="24000-120">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="24000-120">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="24000-121">[Spécifier les informations d’identification et de connexion pour les sources de données de rapport] (.. /Report-Data/Specify-Credential-and-Connection-information-for-Report-Data-sources.MD [serveur de rapports dans Management Studio aide (F1](report-server-in-management-studio-f1-help.md) )</span><span class="sxs-lookup"><span data-stu-id="24000-121">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md [Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md)</span></span>  
  
  
