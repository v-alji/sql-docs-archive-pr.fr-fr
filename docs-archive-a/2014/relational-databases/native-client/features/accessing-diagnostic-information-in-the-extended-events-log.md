---
title: Accès aux informations de diagnostic dans le journal des événements étendus | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: aaa180c2-5e1a-4534-a125-507c647186ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 5148683d464f06e8a4f52cc924baaacac9102b12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698106"
---
# <a name="accessing-diagnostic-information-in-the-extended-events-log"></a><span data-ttu-id="a757d-102">Accès aux informations de diagnostic dans le journal des événements étendus</span><span class="sxs-lookup"><span data-stu-id="a757d-102">Accessing Diagnostic Information in the Extended Events Log</span></span>
  <span data-ttu-id="a757d-103">À compter de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] suivi Native Client et d’accès aux données ([suivi d’accès aux données](https://go.microsoft.com/fwlink/?LinkId=125805)) a été mis à jour pour faciliter l’extraction des informations de diagnostic sur les échecs de connexion à partir de la mémoire tampon en anneau de connectivité et des informations sur les performances de l’application à partir du journal des événements étendus.</span><span class="sxs-lookup"><span data-stu-id="a757d-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and data access tracing ([Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805)) have been updated to make it easier to get diagnostic information about connection failures from the connectivity ring buffer and application performance information from the extended events log.</span></span>  
  
 <span data-ttu-id="a757d-104">Pour plus d’informations sur la lecture du journal des événements étendus, consultez [Afficher des données de session d’événements](../../../database-engine/view-event-session-data.md).</span><span class="sxs-lookup"><span data-stu-id="a757d-104">For information about reading the extended events log, see [View Event Session Data](../../../database-engine/view-event-session-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a757d-105">Cette fonctionnalité n'est conçue qu'à des fins de dépannage et de diagnostic et peut ne pas convenir à des fins d'audit ou de sécurité.</span><span class="sxs-lookup"><span data-stu-id="a757d-105">This feature is intended only for troubleshooting and diagnostic purposes and may not be suitable for auditing or security purposes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a757d-106">Notes</span><span class="sxs-lookup"><span data-stu-id="a757d-106">Remarks</span></span>  
 <span data-ttu-id="a757d-107">Pour les opérations de connexion, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client envoie un ID de connexion client.</span><span class="sxs-lookup"><span data-stu-id="a757d-107">For connection operations, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will send a client connection ID.</span></span> <span data-ttu-id="a757d-108">Si la connexion échoue, vous pouvez accéder à la mémoire tampon en anneau de connectivité ([résolution des problèmes de connectivité dans SQL Server 2008 avec la mémoire tampon en anneau de connectivité](https://go.microsoft.com/fwlink/?LinkId=207752)) et rechercher le `ClientConnectionID` champ et obtenir des informations de diagnostic sur l’échec de la connexion.</span><span class="sxs-lookup"><span data-stu-id="a757d-108">If the connection fails, you can access the connectivity ring buffer ([Connectivity troubleshooting in SQL Server 2008 with the Connectivity Ring Buffer](https://go.microsoft.com/fwlink/?LinkId=207752)) and find the `ClientConnectionID` field and get diagnostic information about the connection failure.</span></span> <span data-ttu-id="a757d-109">Les ID de connexion du client sont enregistrés dans la mémoire tampon en anneau uniquement en cas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="a757d-109">Client connection IDs are logged in the ring buffer only if an error occurs.</span></span> <span data-ttu-id="a757d-110">(Si une connexion échoue avant d'envoyer le paquet de préconnexion, un ID de connexion client ne sera pas généré.) L'ID de connexion client est un GUID à 16 octets.</span><span class="sxs-lookup"><span data-stu-id="a757d-110">(If a connection fails before sending the prelogin packet, a client connection ID will not be generated.) The client connection ID is a 16-byte GUID.</span></span> <span data-ttu-id="a757d-111">Vous pouvez également rechercher l'ID de connexion client dans la cible de sortie d'événements étendus, si l'action de `client_connection_id` est ajoutée aux événements dans une session d'événements étendus.</span><span class="sxs-lookup"><span data-stu-id="a757d-111">You can also find the client connection ID in the extended events output target, if the `client_connection_id` action is added to events in an extended events session.</span></span> <span data-ttu-id="a757d-112">Vous pouvez activer le suivi d'accès aux données et réexécuter la commande de connexion, puis observer le champ `ClientConnectionID` dans la trace d'accès aux données pour une opération ayant échoué, si vous avez besoin de davantage d'aide de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="a757d-112">You can enable data access tracing and rerun the connection command and observe the `ClientConnectionID` field in the data access trace for a failed operation, if you need further diagnostic assistance.</span></span>  
  
 <span data-ttu-id="a757d-113">Si vous utilisez ODBC dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client et qu’une connexion est établie, vous pouvez obtenir l’ID de connexion client à l’aide de l' `SQL_COPT_SS_CLIENT_CONNECTION_ID` attribut avec [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="a757d-113">If you are using ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and a connection succeeds, you can get the client connection ID by using the `SQL_COPT_SS_CLIENT_CONNECTION_ID` attribute with [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a757d-114">Native Client envoie également un ID d'activité spécifique à un thread.</span><span class="sxs-lookup"><span data-stu-id="a757d-114">Native Client also sends a thread-specific activity ID.</span></span> <span data-ttu-id="a757d-115">L'ID d'activité est capturé dans les sessions d'événements étendus si les sessions sont démarrées alors que l'option TRACK_CAUSAILITY est activée.</span><span class="sxs-lookup"><span data-stu-id="a757d-115">The activity ID is captured in the extended events sessions if the sessions are started with the TRACK_CAUSAILITY option enabled.</span></span> <span data-ttu-id="a757d-116">En cas de problèmes de performances avec une connexion active, vous pouvez obtenir l'ID d'activité de la trace d'accès aux données du client (champ `ActivityID`), puis rechercher l'ID d'activité dans la sortie des événements étendus.</span><span class="sxs-lookup"><span data-stu-id="a757d-116">For performance issues with an active connection, you can get the activity ID from the client's data access trace (`ActivityID` field) and then locate the activity ID in the extended events output.</span></span> <span data-ttu-id="a757d-117">L'ID d'activité dans les événements étendus est un GUID à 16 octets (différent du GUID de l'ID de connexion client) ajouté avec un numéro de séquence de quatre octets.</span><span class="sxs-lookup"><span data-stu-id="a757d-117">The activity ID in the extended events is a 16-byte GUID (not the same as the GUID for the client connection ID) appended with a four-byte sequence number.</span></span> <span data-ttu-id="a757d-118">Le numéro séquentiel représente l'ordre d'une demande dans un thread et indique l'ordre relatif du traitement par lot et des instructions RPC pour le thread.</span><span class="sxs-lookup"><span data-stu-id="a757d-118">The sequence number represents the order of a request within a thread and indicates the relative ordering of batch and RPC statements for the thread.</span></span> <span data-ttu-id="a757d-119">`ActivityID` est éventuellement envoyé pour les instructions par lots SQL et les demandes RPC lorsque le suivi d'accès aux données est activé et que le 18ème bit dans le mot de configuration de suivi d'accès aux données est activé.</span><span class="sxs-lookup"><span data-stu-id="a757d-119">The `ActivityID` is optionally sent for SQL batch statements and RPC requests when data access tracing is enabled on and the 18th bit in the data access tracing configuration word is turned ON.</span></span>  
  
 <span data-ttu-id="a757d-120">Voici un exemple qui utilise [!INCLUDE[tsql](../../../includes/tsql-md.md)] pour démarrer une session d'événements étendus qui sera stockée dans une mémoire tampon en anneau et enregistrera l'ID d'activité envoyé d'un client sur des opérations de traitement par lot et RPC.</span><span class="sxs-lookup"><span data-stu-id="a757d-120">The following is a sample that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to start an extended events session that will be stored in a ring buffer and will record the activity ID sent from a client on RPC and batch operations.</span></span>  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
  
```  
  
## <a name="control-file"></a><span data-ttu-id="a757d-121">Fichier de contrôle</span><span class="sxs-lookup"><span data-stu-id="a757d-121">Control File</span></span>  
 <span data-ttu-id="a757d-122">Dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], le contenu du fichier de commandes SQL Server Native Client (ctrl.guid.snac11) est :</span><span class="sxs-lookup"><span data-stu-id="a757d-122">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client control file (ctrl.guid.snac11) is:</span></span>  
  
```  
{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}  0x00000000  0   MSDADIAG.ETW  
{2DA81B52-908E-7DB6-EF81-76856BB47C4F}  0xFFFFFFFF  0   SQLNCLI11.1  
```  
  
## <a name="mof-file"></a><span data-ttu-id="a757d-123">Fichier MOF</span><span class="sxs-lookup"><span data-stu-id="a757d-123">MOF File</span></span>  
 <span data-ttu-id="a757d-124">Dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], le contenu du fichier MOF de SQL Server Native Client est :</span><span class="sxs-lookup"><span data-stu-id="a757d-124">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client mof file is:</span></span>  
  
```  
#pragma classflags("forceupdate")  
#pragma namespace ("\\\\.\\Root\\WMI")  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  MSDADIAG.ETW  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F3-3CC6-0B9C-6651-9649CCE5C752}"),  
 DisplayName("msdadiag"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace : Bid2Etw_MSDADIAG_ETW  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextA : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextW : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  SQLNCLI11.1  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B52-908E-7DB6-EF81-76856BB47C4F}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1 : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B53-908E-7DB6-EF81-76856BB47C4F}"),  
 DisplayName("SQLNCLI11.1"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace : Bid2Etw_SQLNCLI11_1  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextA : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextW : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="a757d-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a757d-125">See Also</span></span>  
 [<span data-ttu-id="a757d-126">Gestion des erreurs et des messages</span><span class="sxs-lookup"><span data-stu-id="a757d-126">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
  
