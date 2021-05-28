---
title: Konfigurowanie parametrów podatku TDS w modułach Rozrachunki z dostawcami i Rozrachunki z odbiorcami
description: W tym temacie wyjaśniono, jak ustawić parametry w rozrachunkach z dostawcami i rozrachunkach z odbiorcami w celu obsługi potrąceń podatku u źródła (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 4540cdfff2362d8fb7cc2b4cccf9c340be9750ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023508"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a><span data-ttu-id="72a9a-103">Konfigurowanie parametrów podatku TDS w modułach Rozrachunki z dostawcami i Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="72a9a-103">Set TDS parameters in Accounts payable and Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72a9a-104">W tym temacie wyjaśniono, jak ustawić parametry w rozrachunkach z dostawcami i rozrachunkach z odbiorcami w celu obsługi potrąceń podatku u źródła (TDS).</span><span class="sxs-lookup"><span data-stu-id="72a9a-104">This topic explains how to set parameters in Accounts payable and Accounts receivable to support Tax Deducted at Source (TDS) deductions.</span></span>

1. <span data-ttu-id="72a9a-105">Wybierz kolejno pozycje **Tax \> Ustawienia \> Parametry \> Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="72a9a-105">Go to **Tax \> Setup \> Parameters \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="72a9a-106">Na karcie **Aktualizacje** wybierz opcję **Aktualizuj wiersze zamówienia**, aby otworzyć okno dialogowe **Aktualizacja wierszy zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="72a9a-106">On the **Updates** tab, select **Update order lines** to open the **Update order lines** dialog box.</span></span>
3. <span data-ttu-id="72a9a-107">W sekcji **Grupa TDS**, w polu **Aktualizacja grupy TDS** określ metodę aktualizacji grupy TDS na poziomie wiersza.</span><span class="sxs-lookup"><span data-stu-id="72a9a-107">In the **TDS group** section, in the **Updating TDS group** field, specify the method to use to update the TDS group at the line level.</span></span> <span data-ttu-id="72a9a-108">To ustawienie jest używane podczas aktualizowania grupy TDS w nagłówku zamówienia.</span><span class="sxs-lookup"><span data-stu-id="72a9a-108">This setting is used when the TDS group is updated on an order header.</span></span> <span data-ttu-id="72a9a-109">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="72a9a-109">The following options are available:</span></span>

    - <span data-ttu-id="72a9a-110">**Nigdy** — grupa TDS nie jest aktualizowana w wierszach zamówienia, gdy jest aktualizowana w nagłówku zamówienia.</span><span class="sxs-lookup"><span data-stu-id="72a9a-110">**Never** – The TDS group isn't updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="72a9a-111">**Zawsze** — Grupa TDS jest automatycznie aktualizowana w wierszach zamówienia, gdy jest aktualizowana w nagłówku zamówienia.</span><span class="sxs-lookup"><span data-stu-id="72a9a-111">**Always** – The TDS group is automatically updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="72a9a-112">**Monituj** — użytkownicy otrzymują komunikat z monitem o aktualizację grupy TDS w wierszach zamówienia.</span><span class="sxs-lookup"><span data-stu-id="72a9a-112">**Prompt** – Users receive a message that prompts them to update the TDS group on the order lines.</span></span>
4. <span data-ttu-id="72a9a-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="72a9a-113">Select **OK**.</span></span>

    <span data-ttu-id="72a9a-114">[![Okno dialogowe aktualizacji wierszy zamówienia](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span><span class="sxs-lookup"><span data-stu-id="72a9a-114">[![Update order lines dialog box](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span></span>

5. <span data-ttu-id="72a9a-115">Wybierz kolejno pozycje **Tax \> Ustawienia \> Parametry \> Parametry modułu rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="72a9a-115">Go to **Tax \> Setup \> Parameters \> Accounts payable parameters**.</span></span>
6. <span data-ttu-id="72a9a-116">Na karcie **Ogólne**, na skróconej karcie **Podziel na podstawie informacji o dostawie** dla opcji **Dokumentu przyjęcia produktów** ustaw wartość **Tak** daby zakwitować i podzielić przyjęcie produktów, które ma różne adresy dostawy i numery kont podatkowych (TAN).</span><span class="sxs-lookup"><span data-stu-id="72a9a-116">On the **General** tab, on the **Split based on delivery information** FastTab, set the **Product receipt** option to **Yes** to post and split a product receipt that has different delivery addresses and tax account numbers (TANs).</span></span> <span data-ttu-id="72a9a-117">Jeśli ta opcja ma wartość **Nie**, nie można zakłać dokumentu dostawy zakupu, który ma różne adresy dostawy i ten typ.</span><span class="sxs-lookup"><span data-stu-id="72a9a-117">If this option is set to **No**, you can't post a purchase packing slip that has different delivery addresses and TANs.</span></span>
7. <span data-ttu-id="72a9a-118">Ustaw dla **faktury** wartość **Tak**, aby zakturować i podzielić fakturę zakupu, która ma różne adresy dostawy i numer TAN.</span><span class="sxs-lookup"><span data-stu-id="72a9a-118">Set the **Invoice** option to **Yes** to post and split a purchase invoice that has different delivery addresses and TANs.</span></span>

    <span data-ttu-id="72a9a-119">[![Podział na podstawie informacji o dostawie Skrócona karta](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span><span class="sxs-lookup"><span data-stu-id="72a9a-119">[![Split based on delivery information FastTab](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span></span>

8. <span data-ttu-id="72a9a-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="72a9a-120">Close the page.</span></span>
