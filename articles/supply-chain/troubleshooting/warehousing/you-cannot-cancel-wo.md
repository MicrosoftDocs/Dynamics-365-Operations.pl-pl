---
title: Nie można anulować pracy dotyczącej użytkownika
description: Nie można anulować pracy dotyczącej użytkownika
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924408"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a><span data-ttu-id="c158c-103">Nie można anulować pracy dotyczącej użytkownika</span><span class="sxs-lookup"><span data-stu-id="c158c-103">You can't cancel work that is on a user</span></span>

<span data-ttu-id="c158c-104">Kod błędu: WAX708</span><span class="sxs-lookup"><span data-stu-id="c158c-104">Error code: WAX708</span></span>

## <a name="symptoms"></a><span data-ttu-id="c158c-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="c158c-105">Symptoms</span></span>

<span data-ttu-id="c158c-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="c158c-106">The system shows the following error message:</span></span>

> <span data-ttu-id="c158c-107">Nie można anulować pracy przypisanej do użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c158c-107">You cannot cancel work that is on a user.</span></span>

## <a name="cause"></a><span data-ttu-id="c158c-108">Powód</span><span class="sxs-lookup"><span data-stu-id="c158c-108">Cause</span></span>

<span data-ttu-id="c158c-109">Praca jest zablokowana przez użytkownika i nie można jej anulować.</span><span class="sxs-lookup"><span data-stu-id="c158c-109">The work is locked by a user and can't be canceled.</span></span> <span data-ttu-id="c158c-110">Aby to potwierdzić, otwórz identyfikator pracy, a następnie otwórz kartę **Ogólne**. Jeśli praca jest zablokowana, pole **Stan pracy** będzie mieć wartość *W toku*, a w polu **Zablokowane przez** będzie identyfikator użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c158c-110">To confirm this, open the work ID and then open the **General** tab. If the work is locked, the **Work status** field will be set to *In progress*, and the **Locked by** field will be set to a user ID.</span></span>

## <a name="resolution"></a><span data-ttu-id="c158c-111">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="c158c-111">Resolution</span></span>

<span data-ttu-id="c158c-112">Aby anulować pracę, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c158c-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="c158c-113">Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="c158c-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="c158c-114">W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować.</span><span class="sxs-lookup"><span data-stu-id="c158c-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="c158c-115">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c158c-115">Select **OK**.</span></span>
1. <span data-ttu-id="c158c-116">Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.</span><span class="sxs-lookup"><span data-stu-id="c158c-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="c158c-117">Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="c158c-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
