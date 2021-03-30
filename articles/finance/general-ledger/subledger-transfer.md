---
title: Przenieś podksięgę do księgi głównej
description: W tym temacie opisano możliwości rozwiązania Microsoft Dynamics 365 Finance związane z procesem przenoszenia księgi podrzędnej w księdze głównej.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: aec68b9389ee2ef28e8119087392ac5f18ec5dd2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204792"
---
# <a name="subledger-transfer-to-the-general-ledger"></a><span data-ttu-id="346c5-103">Przenieś podksięgę do księgi głównej</span><span class="sxs-lookup"><span data-stu-id="346c5-103">Subledger transfer to the General ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="346c5-104">W tym temacie opisano możliwości rozwiązania Microsoft Dynamics 365 Finance, które są związane z regułami przenoszenia partii zapisów w arkuszu księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="346c5-104">This topic describes capabilities in Microsoft Dynamics 365 Finance that are related to the rules for transferring batches of subledger journal entries.</span></span>

<span data-ttu-id="346c5-105">W wersji 8.1 wprowadzono zmiany umożliwiające przeniesienie reguł, które nie wykluczają opcji **Synchronicznie**.</span><span class="sxs-lookup"><span data-stu-id="346c5-105">In version 8.1, changes were made to allow the transfer of rules, which deprecated the **Synchronous** option.</span></span> <span data-ttu-id="346c5-106">Aby uzyskać więcej informacji, zobacz [Usunięte i przestarzałe funkcje w Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span><span class="sxs-lookup"><span data-stu-id="346c5-106">For more information, see [Removed or deprecated features for Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span></span>

<span data-ttu-id="346c5-107">Dostępne są następujące opcje przenoszenia partii w księdze podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="346c5-107">The following options are available for transferring subledger batches.</span></span> 

 - <span data-ttu-id="346c5-108">Asynchroniczne — ta opcja powoduje natychmiastowe zaplanowanie przenoszenia zapisów księgowych księgi podrzędnej do księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="346c5-108">Asynchronous – This option will immediately schedule the transfer of the subledger accounting entries to the general ledger.</span></span> <span data-ttu-id="346c5-109">Załącznik księgi głównej zostanie zarejestrowany, gdy tylko zasoby będą wolne do przetworzenia tego żądania na serwerze.</span><span class="sxs-lookup"><span data-stu-id="346c5-109">The general ledger voucher will be recorded as soon as resources are free to process this request on the server.</span></span> 

- <span data-ttu-id="346c5-110">Zaplanowana partia — ta opcja spowoduje dodanie zapisów księgowych z księgi, które są przenoszone do kolejki przetwarzania w księdze głównej, gdzie zapisy będą przetwarzane w zleceniu otrzymanym.</span><span class="sxs-lookup"><span data-stu-id="346c5-110">Scheduled batch – This option will add the subledger accounting entries that are being transferred to the processing queue in the general ledger, where the entries will be processed in order received.</span></span> <span data-ttu-id="346c5-111">Załącznik księgi głównej zostanie zarejestrowany o określonym czasie, gdy tylko zasoby będą wolne do przetworzenia tego zadania wsadowego na serwerze.</span><span class="sxs-lookup"><span data-stu-id="346c5-111">The general ledger voucher will be recorded at the scheduled time if resources are free to process this batch job on the server.</span></span> 
 
<span data-ttu-id="346c5-112">W wersji 10.0.8 dokonano ulepszeń w celu zwiększenia wydajności opcji asynchronicznej.</span><span class="sxs-lookup"><span data-stu-id="346c5-112">In version 10.0.8, improvements were made to enhance the performance of the Asynchronous option.</span></span> <span data-ttu-id="346c5-113">Ta funkcja jest włączana pod nazwą **optymalizacji wydajności transferu podksięgi do księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="346c5-113">This feature is enabled under the feature name **Subledger transfer to General Ledger performance optimization**.</span></span> 
 
<span data-ttu-id="346c5-114">Ta funkcja poprawia przeniesienie danych z księgi podrzędnej do księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="346c5-114">This functionality improves the transfer of data from the subledger to the general ledger.</span></span> <span data-ttu-id="346c5-115">Dzięki temu proces jest bardziej wydajny i grupuje w nim zestawy mniejszych transakcji do przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="346c5-115">It allows the process to be more efficient, and it groups together sets of smaller transactions to transfer.</span></span> <span data-ttu-id="346c5-116">Pozwala to na wydajniejsze korzystanie z serwera przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="346c5-116">This allows for a more efficient use of the batch server.</span></span> <span data-ttu-id="346c5-117">Ta funkcja wymaga skonfigurowania serwera przetwarzania wsadowego, trybu online i działania, aby można było korzystać z opcji transferu asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="346c5-117">This functionality requires that the batch server be set up, online, and functioning in order for the Asynchronous transfer option to work.</span></span> 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]