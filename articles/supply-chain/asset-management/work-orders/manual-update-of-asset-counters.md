---
title: Ręczna aktualizacja liczników zasobów
description: W tym temacie opisano ręczną aktualizację liczników składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875842"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="b61d0-103">Ręczna aktualizacja liczników zasobów</span><span class="sxs-lookup"><span data-stu-id="b61d0-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="b61d0-104">Liczniki służą do tworzenia rejestracji w składniku majątku, dotyczących na przykład liczby godzin w operacji lub liczby wyprodukowanych ilości.</span><span class="sxs-lookup"><span data-stu-id="b61d0-104">Counters are used to create registrations on an asset regarding, for example, number of hours in operation, or the number of quantities produced.</span></span>

<span data-ttu-id="b61d0-105">Jeśli typ licznika wybrany dla licznika jest ustawiony na dziedziczenie wartości liczników (**Zarządzanie składnikami majątku** > **Ustawienia** > **Typy składników majątku** > **Liczniki** > **Ogólne** karta skrócona > **Dziedzicz wartości licznika** przycisk jest ustawiony na „tak”), a po utworzeniu nowego wiersza licznika tego typu każdy podrzędny składnik, który używa tego samego typu licznika, zostanie automatycznie zaktualizowany.</span><span class="sxs-lookup"><span data-stu-id="b61d0-105">If the counter type selected for a counter is set to inherit counter values (**Asset management** > **Setup** > **Asset types** > **Counters** > **General** FastTab > **Inherit asset counter values** toggle button set to "Yes"), then, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="b61d0-106">W **Wszystkie składniki majątku** można tworzyć godziny lub rejestracje liczników ilości dla składnika w oparciu o odczyty w składniku.</span><span class="sxs-lookup"><span data-stu-id="b61d0-106">In **All assets**, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="b61d0-107">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="b61d0-107">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="b61d0-108">Wybierz składnik majątku z listy i kliknij przycisk **Liczniki**.</span><span class="sxs-lookup"><span data-stu-id="b61d0-108">Select the asset in the list, and click **Counters**.</span></span> <span data-ttu-id="b61d0-109">W formularzu **Liczniki składników majątku** zostanie wyświetlona lista wszystkich poprzednich rejestracji liczników dla wybranego składnika.</span><span class="sxs-lookup"><span data-stu-id="b61d0-109">In the **Asset counters** form, you see a list of all previous counter registrations on the selected asset.</span></span>

3. <span data-ttu-id="b61d0-110">Kliknij przycisk **Nowy**, aby utworzyć nowe rejestracje.</span><span class="sxs-lookup"><span data-stu-id="b61d0-110">Click **New** to create a new registration.</span></span> <span data-ttu-id="b61d0-111">Automatycznie wstawiany jest identyfikator składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b61d0-111">The asset ID is automatically inserted.</span></span>

4. <span data-ttu-id="b61d0-112">W polu **Licznik** wybierz odpowiedni licznik.</span><span class="sxs-lookup"><span data-stu-id="b61d0-112">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="b61d0-113">Dostępne są tylko liczniki powiązane z typem składnika wybranego w obszarze zawartości.</span><span class="sxs-lookup"><span data-stu-id="b61d0-113">Only counters related to the asset type selected on the asset are available.</span></span> <span data-ttu-id="b61d0-114">Jednostka powiązana jest automatycznie wstawiana w polu **Jednostka**.</span><span class="sxs-lookup"><span data-stu-id="b61d0-114">The related unit is automatically inserted in the **Unit** field.</span></span>

5. <span data-ttu-id="b61d0-115">Wybierz datę i godzinę rejestracji licznika.</span><span class="sxs-lookup"><span data-stu-id="b61d0-115">Select date and time for the counter registration.</span></span>

6. <span data-ttu-id="b61d0-116">W polu **Wartość** wstaw numer od ostatniej rejestracji licznika lub, w polu **Zagregowana wartość**, wstaw łączny numer licznika.</span><span class="sxs-lookup"><span data-stu-id="b61d0-116">In the **Value** field, insert the number since the last counter registration, or, in the **Aggregated value** field, insert the total count number.</span></span>

- <span data-ttu-id="b61d0-117">W przypadku fizycznego zainstalowania nowego licznika dla środka trwałego należy zarejestrować zmianę składnika majątku w **Liczniki składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="b61d0-117">If you physically install a new counter on an asset, you need to register the change on the asset in **Asset counters**.</span></span> <span data-ttu-id="b61d0-118">Następnie należy utworzyć dwa wiersze rejestracji o identycznych sygnaturach czasowych, a w wierszu dotyczącym nowego licznika zaznaczyć pole wyboru **Resetuj licznik**.</span><span class="sxs-lookup"><span data-stu-id="b61d0-118">Next, you must create two registration lines with identical timestamps, and on the line regarding the new counter, you select the **Counter reset** check box.</span></span> <span data-ttu-id="b61d0-119">Podczas tworzenia dwóch wierszy rejestracji pierwszy wiersz musi dotyczyć zastępowanego licznika.</span><span class="sxs-lookup"><span data-stu-id="b61d0-119">When you create the two registration lines, the first line must be for the counter that you are replacing.</span></span> <span data-ttu-id="b61d0-120">W polu **Sumy całkowite** liczba jest sumą wszystkich zarejestrowanych wartości licznika z danego typu licznika.</span><span class="sxs-lookup"><span data-stu-id="b61d0-120">In the **Totals** field, the total count number is the sum of the counter total of all registered values on that counter type.</span></span>  
- <span data-ttu-id="b61d0-121">Jeśli zaznaczono pole wyboru **Resetuj licznik** na składniku majątku, należy użyć planu konserwacji z opcją „jeden raz od...” lub „po osiągnięciu...” typ interwału, licznik jest nadal aktywny w nowym wierszu licznika, ponieważ tworzona jest oddzielna linia licznika i rozpoczyna się od nowego licznika.</span><span class="sxs-lookup"><span data-stu-id="b61d0-121">If the **Counter reset** check box is selected on an asset using a maintenance plan with a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line because you create a separate counter line and start over with a new counter.</span></span>

![Rysunek 1](media/11-work-orders.png)


<span data-ttu-id="b61d0-123">Jeśli konieczne jest wprowadzenie rejestracji liczników dla kilku składników majątku, można tego dokonać w **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Liczniki składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="b61d0-123">If you need to make counter registrations on several assets, that can be done in **Asset management** > **Inquiries** > **Assets** > **Asset counters**.</span></span>

>[!NOTE]
><span data-ttu-id="b61d0-124">Istnieje możliwość skonfigurowania zakresu w celu zdefiniowania odchyleń dla ręcznych rejestracji licznika oraz typu komunikatu, który ma być wyświetlany, jeśli rejestracje znajdują się poza zdefiniowanym zakresem.</span><span class="sxs-lookup"><span data-stu-id="b61d0-124">You can set up a range to define deviations in manual counter registrations, and the type of message that should be displayed if registrations are outside the defined range.</span></span> <span data-ttu-id="b61d0-125">Należy zapoznać się z tematem [Liczniki](../setup-for-objects/counters.md), aby zobaczyć konfigurację liczników.</span><span class="sxs-lookup"><span data-stu-id="b61d0-125">Refer to the [Counters](../setup-for-objects/counters.md) topic regarding setup of counters.</span></span>
