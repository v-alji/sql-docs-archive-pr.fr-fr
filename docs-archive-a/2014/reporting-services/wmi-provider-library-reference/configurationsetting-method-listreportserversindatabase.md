---
title: ListReportServersInDatabase, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ListReportServersInDatabase method
ms.assetid: a4bf5968-c46f-484f-a510-65e2dde65a0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9eaea72c0737124d89c86b55281326073597fb38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604359"
---
# <a name="listreportserversindatabase-method-wmi-msreportserver_configurationsetting"></a>Méthode ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting)
  Retourne la liste des installations du serveur de rapports qui sont présentes dans la base de données du serveur de rapports, même si elles n'ont pas accès aux informations sécurisées.  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
Public Sub ListReportServersInDatabase(ByRef MachineNames() As String, _  
    ByRef InstanceNames() As String, ByRef InstallationIDs() As String, _  
    ByRef IsInitialized() As Boolean, ByRef Length As Int32, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] MachineNames,   
    out string[] InstanceNames, out string[] InstallationIDs,   
    out Boolean[] IsInitialized,out Int32 Length, out Int32 HRESULT,    
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a>Paramètres  
 *MachineNames[]*  
 [out] Tableau contenant les noms de machines des installations du serveur de rapports dans la base de données.  
  
 *InstanceNames[]*  
 [out] Tableau contenant les noms d'instances de chacune des installations du serveur de rapports dans la base de données.  
  
 *InstallationIDs[]*  
 [out] Tableau contenant l'ID d'installation de chaque installation du serveur de rapports dans la base de données.  
  
 *IsInitialized[]*  
 [out] Tableau contenant l'état d'initialisation de chaque installation du serveur de rapports dans la base de données.  
  
 *Longueur*  
 [out] Longueur des tableaux retournés par la méthode. Tous les tableaux retournés ont la même longueur.  
  
 *HRESULT*  
 [out] Valeur indiquant si l'appel a réussi ou échoué.  
  
 *ExtendedErrors[]*  
 [out] Tableau de chaînes contenant les erreurs supplémentaires retournées par l'appel.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué. Une valeur 0 indique que l'appel de méthode a réussi. Une valeur différente de zéro indique qu'une erreur s'est produite.  
  
## <a name="remarks"></a>Notes  
 ListReportServersInDatabase répertorie les installations du serveur de rapports qui sont présentes dans la base de données du serveur de rapports, qu’elles aient accès ou non aux informations sécurisées, et retourne un ensemble de tableaux correspondants qui contiennent des informations à propos de chaque installation.  
  
## <a name="requirements"></a>Spécifications  
 **Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Membres MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  
