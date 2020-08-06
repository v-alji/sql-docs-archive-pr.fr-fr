---
title: Propriétés de Protocoles pour MSSQLSERVER (onglet Certificat) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.computermgr.cert.general.f1
helpviewer_keywords:
- MSSQLSERVER property protocols
ms.assetid: 776addd6-25f3-4875-9a71-064035787090
author: stevestein
ms.author: sstein
ms.openlocfilehash: 020d33eba7621f877f8622ca89dbd26a071f16a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705775"
---
# <a name="protocols-for-mssqlserver-properties-certificate-tab"></a><span data-ttu-id="637d1-102">Propriétés de Protocoles pour MSSQLSERVER (onglet Certificat)</span><span class="sxs-lookup"><span data-stu-id="637d1-102">Protocols for MSSQLSERVER Properties (Certificate Tab)</span></span>
  <span data-ttu-id="637d1-103">L'onglet **Certificat** de la boîte de dialogue **Propriétés de Protocoles pour MSSQLSERVER** vous permet de sélectionner un certificat pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'afficher les propriétés d'un certificat.</span><span class="sxs-lookup"><span data-stu-id="637d1-103">Use the **Certificate** tab on the **Protocols for MSSQLSERVER Properties** dialog box to select a certificate for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or to view the properties of a certificate.</span></span> <span data-ttu-id="637d1-104">Tous les champs sont vides tant qu'aucun certificat n'est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="637d1-104">All fields are blank until a certificate is selected.</span></span>  
  
 <span data-ttu-id="637d1-105">Les certificats sont stockés localement pour les utilisateurs de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="637d1-105">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="637d1-106">Pour charger un certificat en vue de son utilisation par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous devez exécuter le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sous le même compte d'utilisateur que le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="637d1-106">To load a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="637d1-107">En-tête de page</span><span class="sxs-lookup"><span data-stu-id="637d1-107">Page Header</span></span>  
 <span data-ttu-id="637d1-108">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="637d1-108">**View**</span></span>  
 <span data-ttu-id="637d1-109">Fournit des détails supplémentaires sur le certificat.</span><span class="sxs-lookup"><span data-stu-id="637d1-109">Provides access to additional details on the certificate.</span></span> <span data-ttu-id="637d1-110">Cette option n'est disponible qu'une fois qu'un certificat est sélectionné dans la zone **Certificat** .</span><span class="sxs-lookup"><span data-stu-id="637d1-110">Not available until a certificate is selected in the **Certificate** box.</span></span> <span data-ttu-id="637d1-111">Pour plus d'informations sur les détails des certificats, consultez la documentation [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="637d1-111">For additional information on certificate details, see your [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
 <span data-ttu-id="637d1-112">**Clear**</span><span class="sxs-lookup"><span data-stu-id="637d1-112">**Clear**</span></span>  
 <span data-ttu-id="637d1-113">Supprime la sélection de la zone **Certificat** .</span><span class="sxs-lookup"><span data-stu-id="637d1-113">Removes the selection from the **Certificate** box.</span></span>  
  
 <span data-ttu-id="637d1-114">**Certificate**</span><span class="sxs-lookup"><span data-stu-id="637d1-114">**Certificate**</span></span>  
 <span data-ttu-id="637d1-115">Nom de certificat tel que déterminé par le fournisseur de sécurité.</span><span class="sxs-lookup"><span data-stu-id="637d1-115">Name of certificate as determined by security provider.</span></span> <span data-ttu-id="637d1-116">Sélectionnez un certificat pour en afficher les détails dans la grille des propriétés.</span><span class="sxs-lookup"><span data-stu-id="637d1-116">Select a certificate to see the details in the properties grid.</span></span>  
  
## <a name="options"></a><span data-ttu-id="637d1-117">Options</span><span class="sxs-lookup"><span data-stu-id="637d1-117">Options</span></span>  
 <span data-ttu-id="637d1-118">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="637d1-118">Expiration Date</span></span>  
 <span data-ttu-id="637d1-119">Date de fin de la période de validité du certificat.</span><span class="sxs-lookup"><span data-stu-id="637d1-119">The final date for the period in which the certificate is valid.</span></span>  
  
 <span data-ttu-id="637d1-120">Nom convivial</span><span class="sxs-lookup"><span data-stu-id="637d1-120">Friendly Name</span></span>  
 <span data-ttu-id="637d1-121">Nom convivial ou courant représentant la personne ou l'Autorité de certification destinataire du certificat.</span><span class="sxs-lookup"><span data-stu-id="637d1-121">A friendly or common name for the individual or certification authority to whom the certificate is issued.</span></span>  
  
 <span data-ttu-id="637d1-122">Émis par</span><span class="sxs-lookup"><span data-stu-id="637d1-122">Issued By</span></span>  
 <span data-ttu-id="637d1-123">Informations relatives à l'Autorité de certification qui a émis le certificat.</span><span class="sxs-lookup"><span data-stu-id="637d1-123">Information regarding the certification authority that issued the certificate.</span></span>  
  
 <span data-ttu-id="637d1-124">Délivré à</span><span class="sxs-lookup"><span data-stu-id="637d1-124">Issued To</span></span>  
 <span data-ttu-id="637d1-125">Informations relatives au destinataire du certificat.</span><span class="sxs-lookup"><span data-stu-id="637d1-125">Information regarding the recipient of the certificate.</span></span>  
  
  
