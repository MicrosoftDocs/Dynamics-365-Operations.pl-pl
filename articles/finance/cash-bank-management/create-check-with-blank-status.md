---
title: Tworzenie czeków z pustym statusem
description: W tym temacie wyjaśniono, jak tworzyć puste czeki dla konta bankowego na stronie Czeki.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 94d3a4ac8a3906e48f5a6053c031001c111549ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254042"
---
# <a name="create-checks-that-have-blank-status"></a><span data-ttu-id="84683-103">Tworzenie czeków z pustym statusem</span><span class="sxs-lookup"><span data-stu-id="84683-103">Create checks that have Blank status</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84683-104">W tym temacie wyjaśniono, jak tworzyć puste czeki.</span><span class="sxs-lookup"><span data-stu-id="84683-104">This topic explains how to create blank checks.</span></span> <span data-ttu-id="84683-105">Na przykład możesz utworzyć pusty czek, aby zarejestrować czek, który został uszkodzony i nie można go wykorzystać do płatności.</span><span class="sxs-lookup"><span data-stu-id="84683-105">For example, you might create a blank check to record a check that has been damaged and can't be used for payment.</span></span>

<span data-ttu-id="84683-106">Na stronie **Czeki** wykonuje się zadania konserwacyjne związane z czekami.</span><span class="sxs-lookup"><span data-stu-id="84683-106">On the **Checks** page, you perform maintenance tasks for checks.</span></span> <span data-ttu-id="84683-107">Na przykład możesz tworzyć nowe numery czeków i usuwać czeki.</span><span class="sxs-lookup"><span data-stu-id="84683-107">For example, you can create new check numbers and delete checks.</span></span> <span data-ttu-id="84683-108">Możesz także tworzyć czeki o statusie **Pusty**.</span><span class="sxs-lookup"><span data-stu-id="84683-108">You can also create checks that have a status of **Blank**.</span></span> <span data-ttu-id="84683-109">Po utworzeniu pustych czeków nie można ich usunąć ani użyć ponownie w systemie.</span><span class="sxs-lookup"><span data-stu-id="84683-109">After blank checks are created, they can't be deleted or reused in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="84683-110">Ta funkcja jest dostępna na stronie **Czeki** tylko jeśli włączysz funkcję **Twórz czeki z pustym statusem na stronie Czeki** na stronie **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="84683-110">This feature is available on the **Checks** page only if you turn on the **Create checks with a blank status on the Checks page** feature on the **Feature management** page.</span></span> <span data-ttu-id="84683-111">Jeśli ta funkcja nie jest włączona, czeki o statusie **Pusty** można utworzyć tylko w oknie dialogowym **Płatność czekiem** podczas procesu generowania płatności w opcji Rozrachunki z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="84683-111">If the feature isn't turned on, checks that have **Blank** status can be created only from the **Payment by check** dialog box during the payment generation process in Accounts payable.</span></span>

<span data-ttu-id="84683-112">Aby otworzyć stronę **Czeki**, przejdź do **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**, a następnie w okienku akcji na karcie **Zarządzanie płatnościami** w grupie **Informacje pokrewne**, wybierz opcję **Czeki**.</span><span class="sxs-lookup"><span data-stu-id="84683-112">To open the **Checks** page, go to **Cash and bank management \> Bank accounts \> Bank accounts**, and then, on the Action Pane, on the **Manage payments** tab, in the **Related information** group, select **Checks**.</span></span> <span data-ttu-id="84683-113">Możesz też wybrać opcje **Zarządzanie gotówką i bankami \> Zapytania i raporty \> Czeki**.</span><span class="sxs-lookup"><span data-stu-id="84683-113">Alternatively, go to **Cash and bank management \> Inquiries and reports \> Checks**.</span></span>

<span data-ttu-id="84683-114">Następnie, aby utworzyć czeki, które mają status **Pusty** w okienku akcji wybierz **Utwórz puste czeki**.</span><span class="sxs-lookup"><span data-stu-id="84683-114">Then, to create checks that have **Blank** status, on the Action Pane, select **Create blank checks**.</span></span> <span data-ttu-id="84683-115">Gdy system tworzy puste czeki, powiązane konto bankowe zostaje tymczasowo dezaktywowane.</span><span class="sxs-lookup"><span data-stu-id="84683-115">While the system is creating blank checks, the associated bank account is temporarily inactivated.</span></span> <span data-ttu-id="84683-116">To zachowanie zmniejsza ryzyko, że płatności będą generowane w tym samym czasie, gdy tworzone są puste czeki.</span><span class="sxs-lookup"><span data-stu-id="84683-116">This behavior reduces the risk that payments will be generated at the same time that blank checks are created.</span></span> <span data-ttu-id="84683-117">Po zakończeniu przetwarzania powiązane konto bankowe zostanie ponownie aktywowane.</span><span class="sxs-lookup"><span data-stu-id="84683-117">When the processing is completed, the associated bank account is reactivated.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]