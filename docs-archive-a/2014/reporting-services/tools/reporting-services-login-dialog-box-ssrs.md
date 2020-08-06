---
title: Ouverture de session Reporting Services, boîte de dialogue (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 232ee51614a668b07263c3e3a4182f23652135bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704835"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a><span data-ttu-id="5d627-102">Ouverture de session Reporting Services, boîte de dialogue (SSRS)</span><span class="sxs-lookup"><span data-stu-id="5d627-102">Reporting Services Login Dialog Box (SSRS)</span></span>
  <span data-ttu-id="5d627-103">Utilisez la boîte de dialogue **Ouverture de session Reporting Services** pour fournir les informations d'identification nécessaires à la publication de rapports sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5d627-103">Use the **Reporting Services Login** dialog box to provide credentials to publish reports to the report server.</span></span>  
  
-   <span data-ttu-id="5d627-104">**Remarque** S'il s'agit de la première fois que vous avez publié un rapport sur un serveur de rapports depuis que vous avez défini la propriété de déploiement **TargetServerURL** pour un projet, vérifiez que le nom du serveur que vous avez spécifié est semblable à `http://localhost/reportserver`, et non à `http://localhost/reports`.</span><span class="sxs-lookup"><span data-stu-id="5d627-104">**Note** If this is the first time you have published a report to a report server since set you set the deployment property **TargetServerURL** for a project, verify that the server name you specified is similar to `http://localhost/reportserver`, and not `http://localhost/reports`.</span></span> <span data-ttu-id="5d627-105">La spécification du répertoire `reports` sur le serveur local au lieu du répertoire `reportserver` provoque indirectement l'ouverture de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5d627-105">Specifying the `reports` directory on the local server instead of the `reportserver` directory indirectly causes this dialog box to open.</span></span> <span data-ttu-id="5d627-106">Pour plus d’informations sur la configuration de **TargetServerURL**, consultez [Définir des propriétés de déploiement &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5d627-106">For more information about setting **TargetServerURL**, see [Set Deployment Properties &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5d627-107">Options</span><span class="sxs-lookup"><span data-stu-id="5d627-107">Options</span></span>  
 <span data-ttu-id="5d627-108">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="5d627-108">**Server**</span></span>  
 <span data-ttu-id="5d627-109">Affiche le nom du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5d627-109">Displays the name of the report server.</span></span> <span data-ttu-id="5d627-110">Par exemple : `http://localhost/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="5d627-110">For example, `http://localhost/reportserver`.</span></span> <span data-ttu-id="5d627-111">Pour les serveurs de rapports qui utilisent un autre port que le port par défaut 80, incluez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="5d627-111">For report servers that use a different port than default port 80, include the port number.</span></span> <span data-ttu-id="5d627-112">Par exemple : `http://localhost:81/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="5d627-112">For example, `http://localhost:81/reportserver`.</span></span>  
  
 <span data-ttu-id="5d627-113">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="5d627-113">**User name**</span></span>  
 <span data-ttu-id="5d627-114">Tapez le nom d'utilisateur pour la connexion au service Web.</span><span class="sxs-lookup"><span data-stu-id="5d627-114">Type the user name to log in to the Web service.</span></span>  
  
 <span data-ttu-id="5d627-115">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="5d627-115">**Password**</span></span>  
 <span data-ttu-id="5d627-116">Tapez le mot de passe pour la connexion au service Web.</span><span class="sxs-lookup"><span data-stu-id="5d627-116">Type the password to log in to the Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d627-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d627-117">See Also</span></span>  
 <span data-ttu-id="5d627-118">[Connexions de données, sources de données et chaînes de connexion dans Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="5d627-118">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="5d627-119">[Spécifier les informations d’identification et de connexion pour les sources de données de rapport](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Concepteur de rapports aide F1](report-designer-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="5d627-119">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Report Designer F1 Help](report-designer-f1-help.md)</span></span>  
  
  
