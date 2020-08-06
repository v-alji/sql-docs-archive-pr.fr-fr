---
title: StartService, méthode (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartService method
ms.assetid: 83dfb6bd-dbd5-45d8-aad2-a11926317f91
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4d91646da2ac2c9f636655ff6c65808ba115e28f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702548"
---
# <a name="startservice-method-sqlservice-class"></a><span data-ttu-id="1cd07-102">Méthode StartService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="1cd07-102">StartService Method (SqlService Class)</span></span>
  <span data-ttu-id="1cd07-103">Tente de placer le service dans son état démarré.</span><span class="sxs-lookup"><span data-stu-id="1cd07-103">Attempts to place the service into its started state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cd07-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1cd07-104">Syntax</span></span>  
  
```  
  
object  
.StartService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="1cd07-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="1cd07-105">Parts</span></span>  
 <span data-ttu-id="1cd07-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1cd07-106">*object*</span></span>  
 <span data-ttu-id="1cd07-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="1cd07-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1cd07-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="1cd07-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="1cd07-109">Valeur uint32 qui spécifie l'un des états de démarrage suivants.</span><span class="sxs-lookup"><span data-stu-id="1cd07-109">A uint32 value that specifies one of the following startup states.</span></span>  
  
 <span data-ttu-id="1cd07-110">0</span><span class="sxs-lookup"><span data-stu-id="1cd07-110">0</span></span>  
 <span data-ttu-id="1cd07-111">Réussite.</span><span class="sxs-lookup"><span data-stu-id="1cd07-111">Success.</span></span> <span data-ttu-id="1cd07-112">La demande a été acceptée.</span><span class="sxs-lookup"><span data-stu-id="1cd07-112">The request was accepted.</span></span>  
  
 <span data-ttu-id="1cd07-113">1</span><span class="sxs-lookup"><span data-stu-id="1cd07-113">1</span></span>  
 <span data-ttu-id="1cd07-114">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="1cd07-114">Not Supported.</span></span> <span data-ttu-id="1cd07-115">La demande n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="1cd07-115">The request is not supported.</span></span>  
  
 <span data-ttu-id="1cd07-116">2</span><span class="sxs-lookup"><span data-stu-id="1cd07-116">2</span></span>  
 <span data-ttu-id="1cd07-117">Accès refusé.</span><span class="sxs-lookup"><span data-stu-id="1cd07-117">Access Denied.</span></span> <span data-ttu-id="1cd07-118">L'utilisateur ne disposait pas des droits d'accès appropriés.</span><span class="sxs-lookup"><span data-stu-id="1cd07-118">The user did not have appropriate access.</span></span>  
  
 <span data-ttu-id="1cd07-119">3</span><span class="sxs-lookup"><span data-stu-id="1cd07-119">3</span></span>  
 <span data-ttu-id="1cd07-120">Services dépendants en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1cd07-120">Dependent Services Running.</span></span> <span data-ttu-id="1cd07-121">Le service ne peut pas être arrêté car d'autres services en cours d'exécution en dépendent.</span><span class="sxs-lookup"><span data-stu-id="1cd07-121">The service cannot be stopped because other services that are running are dependent on it.</span></span>  
  
 <span data-ttu-id="1cd07-122">4</span><span class="sxs-lookup"><span data-stu-id="1cd07-122">4</span></span>  
 <span data-ttu-id="1cd07-123">Contrôle de service non valide.</span><span class="sxs-lookup"><span data-stu-id="1cd07-123">Invalid Service Control.</span></span> <span data-ttu-id="1cd07-124">Le code de contrôle demandé n'est pas valide ou est inacceptable pour le service.</span><span class="sxs-lookup"><span data-stu-id="1cd07-124">The requested control code is not valid, or it is unacceptable to the service.</span></span>  
  
 <span data-ttu-id="1cd07-125">5</span><span class="sxs-lookup"><span data-stu-id="1cd07-125">5</span></span>  
 <span data-ttu-id="1cd07-126">Le service n'accepte pas le contrôle.</span><span class="sxs-lookup"><span data-stu-id="1cd07-126">Service Cannot Accept Control.</span></span> <span data-ttu-id="1cd07-127">Le code de contrôle demandé ne peut pas être envoyé au service car l'état du service (Win32_BaseService:State) est égal à 0, 1 ou 2.</span><span class="sxs-lookup"><span data-stu-id="1cd07-127">The requested control code cannot be sent to the service because the state of the service (Win32_BaseService:State) is equal to 0, 1, or 2.</span></span>  
  
 <span data-ttu-id="1cd07-128">6</span><span class="sxs-lookup"><span data-stu-id="1cd07-128">6</span></span>  
 <span data-ttu-id="1cd07-129">Service inactif.</span><span class="sxs-lookup"><span data-stu-id="1cd07-129">Service Not Active.</span></span> <span data-ttu-id="1cd07-130">Le service n'a pas été démarré.</span><span class="sxs-lookup"><span data-stu-id="1cd07-130">The service has not been started.</span></span>  
  
 <span data-ttu-id="1cd07-131">7</span><span class="sxs-lookup"><span data-stu-id="1cd07-131">7</span></span>  
 <span data-ttu-id="1cd07-132">Délai de la demande de service dépassé.</span><span class="sxs-lookup"><span data-stu-id="1cd07-132">Service Request Timeout.</span></span> <span data-ttu-id="1cd07-133">Le service n'a pas répondu à la demande de démarrage en temps voulu.</span><span class="sxs-lookup"><span data-stu-id="1cd07-133">The service did not respond to the start request in a timely fashion.</span></span>  
  
 <span data-ttu-id="1cd07-134">8</span><span class="sxs-lookup"><span data-stu-id="1cd07-134">8</span></span>  
 <span data-ttu-id="1cd07-135">Échec inconnu.</span><span class="sxs-lookup"><span data-stu-id="1cd07-135">Unknown Failure.</span></span> <span data-ttu-id="1cd07-136">Un échec inconnu s'est produit lors du démarrage du service.</span><span class="sxs-lookup"><span data-stu-id="1cd07-136">An unknown failure occurred when starting the service.</span></span>  
  
 <span data-ttu-id="1cd07-137">9</span><span class="sxs-lookup"><span data-stu-id="1cd07-137">9</span></span>  
 <span data-ttu-id="1cd07-138">Chemin d'accès introuvable.</span><span class="sxs-lookup"><span data-stu-id="1cd07-138">Path Not Found.</span></span> <span data-ttu-id="1cd07-139">Le chemin d'accès au répertoire de l'exécutable du service n'a pas été trouvé.</span><span class="sxs-lookup"><span data-stu-id="1cd07-139">The directory path to the service executable was not found.</span></span>  
  
 <span data-ttu-id="1cd07-140">10</span><span class="sxs-lookup"><span data-stu-id="1cd07-140">10</span></span>  
 <span data-ttu-id="1cd07-141">Le service est déjà en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1cd07-141">Service Already Running.</span></span> <span data-ttu-id="1cd07-142">Le service est déjà en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1cd07-142">The service is already running.</span></span>  
  
 <span data-ttu-id="1cd07-143">11</span><span class="sxs-lookup"><span data-stu-id="1cd07-143">11</span></span>  
 <span data-ttu-id="1cd07-144">Base de données du service verrouillée.</span><span class="sxs-lookup"><span data-stu-id="1cd07-144">Service Database Locked.</span></span> <span data-ttu-id="1cd07-145">La base de données pour ajouter un nouveau service est verrouillée.</span><span class="sxs-lookup"><span data-stu-id="1cd07-145">The database to add a new service is locked.</span></span>  
  
 <span data-ttu-id="1cd07-146">12</span><span class="sxs-lookup"><span data-stu-id="1cd07-146">12</span></span>  
 <span data-ttu-id="1cd07-147">Dépendance du service supprimée.</span><span class="sxs-lookup"><span data-stu-id="1cd07-147">Service Dependency Deleted.</span></span> <span data-ttu-id="1cd07-148">Une dépendance sur laquelle repose ce service a été supprimée du système.</span><span class="sxs-lookup"><span data-stu-id="1cd07-148">A dependency on which this service relies has been removed from the system.</span></span>  
  
 <span data-ttu-id="1cd07-149">13</span><span class="sxs-lookup"><span data-stu-id="1cd07-149">13</span></span>  
 <span data-ttu-id="1cd07-150">Échec de la dépendance du service.</span><span class="sxs-lookup"><span data-stu-id="1cd07-150">Service Dependency Failure.</span></span> <span data-ttu-id="1cd07-151">Le service n'a pas pu trouver le service nécessaire à partir d'un service dépendant.</span><span class="sxs-lookup"><span data-stu-id="1cd07-151">The service failed to find the service needed from a dependent service.</span></span>  
  
 <span data-ttu-id="1cd07-152">14</span><span class="sxs-lookup"><span data-stu-id="1cd07-152">14</span></span>  
 <span data-ttu-id="1cd07-153">Service désactivé.</span><span class="sxs-lookup"><span data-stu-id="1cd07-153">Service Disabled.</span></span> <span data-ttu-id="1cd07-154">Le service a été désactivé du système.</span><span class="sxs-lookup"><span data-stu-id="1cd07-154">The service has been disabled from the system.</span></span>  
  
 <span data-ttu-id="1cd07-155">15</span><span class="sxs-lookup"><span data-stu-id="1cd07-155">15</span></span>  
 <span data-ttu-id="1cd07-156">Échec de connexion au service.</span><span class="sxs-lookup"><span data-stu-id="1cd07-156">Service Logon Failed.</span></span> <span data-ttu-id="1cd07-157">Le service ne dispose pas de l'authentification correcte pour être exécuté sur le système.</span><span class="sxs-lookup"><span data-stu-id="1cd07-157">The service does not have the correct authentication to run on the system.</span></span>  
  
 <span data-ttu-id="1cd07-158">16</span><span class="sxs-lookup"><span data-stu-id="1cd07-158">16</span></span>  
 <span data-ttu-id="1cd07-159">Service marqué pour suppression.</span><span class="sxs-lookup"><span data-stu-id="1cd07-159">Service Marked For Deletion.</span></span> <span data-ttu-id="1cd07-160">Le service est en cours de suppression du système.</span><span class="sxs-lookup"><span data-stu-id="1cd07-160">The service is being removed from the system.</span></span>  
  
 <span data-ttu-id="1cd07-161">17</span><span class="sxs-lookup"><span data-stu-id="1cd07-161">17</span></span>  
 <span data-ttu-id="1cd07-162">Service sans thread.</span><span class="sxs-lookup"><span data-stu-id="1cd07-162">Service No Thread.</span></span> <span data-ttu-id="1cd07-163">Il n'y a pas de thread d'exécution pour le service.</span><span class="sxs-lookup"><span data-stu-id="1cd07-163">There is no execution thread for the service.</span></span>  
  
 <span data-ttu-id="1cd07-164">18</span><span class="sxs-lookup"><span data-stu-id="1cd07-164">18</span></span>  
 <span data-ttu-id="1cd07-165">Dépendance circulaire de l'état.</span><span class="sxs-lookup"><span data-stu-id="1cd07-165">Status Circular Dependency.</span></span> <span data-ttu-id="1cd07-166">Le démarrage du service donne lieu à des dépendances circulaires.</span><span class="sxs-lookup"><span data-stu-id="1cd07-166">There are circular dependencies when starting the service.</span></span>  
  
 <span data-ttu-id="1cd07-167">19</span><span class="sxs-lookup"><span data-stu-id="1cd07-167">19</span></span>  
 <span data-ttu-id="1cd07-168">Nom de l'état déjà existant.</span><span class="sxs-lookup"><span data-stu-id="1cd07-168">Status Duplicate Name.</span></span> <span data-ttu-id="1cd07-169">Un service est en cours d'exécution sous le même nom.</span><span class="sxs-lookup"><span data-stu-id="1cd07-169">There is a service running under the same name.</span></span>  
  
 <span data-ttu-id="1cd07-170">20</span><span class="sxs-lookup"><span data-stu-id="1cd07-170">20</span></span>  
 <span data-ttu-id="1cd07-171">Nom de l'état non valide.</span><span class="sxs-lookup"><span data-stu-id="1cd07-171">Status Invalid Name.</span></span> <span data-ttu-id="1cd07-172">Le nom du service contient des caractères non valides.</span><span class="sxs-lookup"><span data-stu-id="1cd07-172">There are characters that are not valid in the name of the service.</span></span>  
  
 <span data-ttu-id="1cd07-173">21</span><span class="sxs-lookup"><span data-stu-id="1cd07-173">21</span></span>  
 <span data-ttu-id="1cd07-174">Paramètre d'état non valide.</span><span class="sxs-lookup"><span data-stu-id="1cd07-174">Status Invalid Parameter.</span></span> <span data-ttu-id="1cd07-175">Des paramètres non valides ont été transmis au service.</span><span class="sxs-lookup"><span data-stu-id="1cd07-175">Parameters that are not valid have been passed to the service.</span></span>  
  
 <span data-ttu-id="1cd07-176">22</span><span class="sxs-lookup"><span data-stu-id="1cd07-176">22</span></span>  
 <span data-ttu-id="1cd07-177">Compte du service d'état non valide.</span><span class="sxs-lookup"><span data-stu-id="1cd07-177">Status Invalid Service Account.</span></span> <span data-ttu-id="1cd07-178">Le compte sous lequel ce service doit s'exécuter n'est pas valide ou il ne dispose pas des autorisations nécessaires pour exécuter le service.</span><span class="sxs-lookup"><span data-stu-id="1cd07-178">The account which this service is to run under is not valid, or it lacks the permissions to run the service.</span></span>  
  
 <span data-ttu-id="1cd07-179">23</span><span class="sxs-lookup"><span data-stu-id="1cd07-179">23</span></span>  
 <span data-ttu-id="1cd07-180">Le service d'état existe déjà.</span><span class="sxs-lookup"><span data-stu-id="1cd07-180">Status Service Exists.</span></span> <span data-ttu-id="1cd07-181">Le service existe dans la base de données des services disponibles dans le système.</span><span class="sxs-lookup"><span data-stu-id="1cd07-181">The service exists in the database of services available from the system.</span></span>  
  
 <span data-ttu-id="1cd07-182">24</span><span class="sxs-lookup"><span data-stu-id="1cd07-182">24</span></span>  
 <span data-ttu-id="1cd07-183">Service déjà en pause.</span><span class="sxs-lookup"><span data-stu-id="1cd07-183">Service Already Paused.</span></span> <span data-ttu-id="1cd07-184">Le service est actuellement mis en pause dans le système.</span><span class="sxs-lookup"><span data-stu-id="1cd07-184">The service is currently paused in the system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cd07-185">Notes</span><span class="sxs-lookup"><span data-stu-id="1cd07-185">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd07-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1cd07-186">See Also</span></span>  
 <span data-ttu-id="1cd07-187">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1cd07-187">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
