---
title: Funkcje dzielenia faktury
description: W tym temacie opisano ustawienia i funkcje dzielenia faktur według adresu dostawy i numeru konta podatkowego (TAN).
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
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023513"
---
# <a name="split-invoice-functionality"></a><span data-ttu-id="5a496-103">Funkcje dzielenia faktury</span><span class="sxs-lookup"><span data-stu-id="5a496-103">Split invoice functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a496-104">W tym temacie opisano ustawienia i funkcje dzielenia faktur według adresu dostawy i numeru konta podatkowego (TAN).</span><span class="sxs-lookup"><span data-stu-id="5a496-104">This topic describes the setup and functionality for splitting invoices by delivery address and tax account number (TAN).</span></span>

<span data-ttu-id="5a496-105">Na stronie **Parametry rozrachunków z dostawcami**, na karcie **Ogólne** zaznacz pole wyboru **Przyjęcie produktu** lub **Faktura**, aby zakwitować i podzielić przyjęcie produktu lub fakturę, która ma różne adresy dostawy i numer TAN na stronie **Zamówienie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="5a496-105">On the **Accounts payable parameters** page, on the **General** tab, select the **Product receipt** or **Invoice** checkbox to post and split a product receipt or invoice that has different delivery addresses and TANs on the **Purchase order** page.</span></span> <span data-ttu-id="5a496-106">Zaksięgowana faktura zostanie następnie podzielona według adresu dostawy i TAN.</span><span class="sxs-lookup"><span data-stu-id="5a496-106">The posted invoice will then be split by delivery address and TAN.</span></span>

<span data-ttu-id="5a496-107">Na karcie **Aktualizacja zbiorcza**, w wierszu **Informacje o dostawie**, w wierszu **Informacji o dostawie**, ustaw opcję **Potwierdzenie**, **Lista pobrania**, **Dokument dostawy** lub **Faktura** na **Tak**, aby zakturować i podzielić potwierdzenie, listę pobrania, dokument dostawy lub fakturę, dla których na stronie **zamówienia sprzedaży** są zdefiniowane różne adresy dostawy i TAN.</span><span class="sxs-lookup"><span data-stu-id="5a496-107">On the **Summary update** tab, on the **Split based on** FastTab, in the **Delivery information** row, set the **Confirmation**, **Picking list**, **Packing slip**, or **Invoice** option to **Yes** to post and split a confirmation, picking list, packing slip, or invoice where different delivery addresses and TANs are defined for different invoice lines on the **Sales order** page.</span></span> <span data-ttu-id="5a496-108">Faktura zostanie podzielona najpierw według adresu dostawy, a następnie według numeru TAN.</span><span class="sxs-lookup"><span data-stu-id="5a496-108">The invoice will be split first by delivery address and then by TAN.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="5a496-109">Jeśli w ustawieniach **informacji o dostawie** nie zostanie ustawiona wartość **Tak**, faktura zostanie zaksięgowana jako jedna faktura.</span><span class="sxs-lookup"><span data-stu-id="5a496-109">If no options for **Delivery information** are set to **Yes**, the invoice will be posted as a single invoice.</span></span> <span data-ttu-id="5a496-110">Nie nastąpi podział faktury.</span><span class="sxs-lookup"><span data-stu-id="5a496-110">No invoice splitting will occur.</span></span>
> - <span data-ttu-id="5a496-111">Aby podzielić i zakturować dokument dostawy, w którym wiersze faktury mają różne adresy dostawy i numer TAN, w opcji **Dokument dostawy** dla **informacji o dostawie** musi być ustawiona wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5a496-111">To split and post a packing slip where the invoice lines have different delivery addresses and TANs, you must set the **Packing slip** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="5a496-112">Aby podzielić i zakturować fakturę, w którym wiersze faktury mają różne adresy dostawy i numer TAN, w opcji **Faktura** dla **informacji o dostawie** musi być ustawiona wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5a496-112">To split and post an invoice where the invoice lines have different delivery addresses and TANs, you must set the **Invoice** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="5a496-113">Aby zaksięgować fakturę, w której wiersze faktury mają różne adresy dostawy, ale ten sam numer TAN, w opcji **Faktura** dla **informacji o dostawie** musi być ustawiona wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="5a496-113">To post an invoice where the invoice lines have different delivery addresses but the same TAN, set the **Invoice** option for **Delivery information** to **No**.</span></span> <span data-ttu-id="5a496-114">Faktura zostanie podzielona najpierw według adresu dostawy.</span><span class="sxs-lookup"><span data-stu-id="5a496-114">The invoice will be split by delivery address.</span></span>

## <a name="example"></a><span data-ttu-id="5a496-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="5a496-115">Example</span></span>

<span data-ttu-id="5a496-116">W tym przykładzie opcja **Faktura** dla **informacji o dostawie** ma wartość **Tak** na karcie **Aktualizacja zbiorcza** na stronie **Parametry rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="5a496-116">In this example, the **Invoice** option for **Delivery information** is set to **Yes** on the **Summary update** tab of the **Accounts payable parameters** page.</span></span> <span data-ttu-id="5a496-117">Księgowana jest faktura zakupu, która zawiera następujące ustawienia adresów dostawy i numerów TAN w wierszach:</span><span class="sxs-lookup"><span data-stu-id="5a496-117">A purchase invoice is posted that has the following setup for delivery addresses and TANs on the lines:</span></span>

- <span data-ttu-id="5a496-118">**Wiersz pozycji 1:** adres dostawy 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="5a496-118">**Item line 1:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="5a496-119">**Wiersz pozycji 2:** adres dostawy 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="5a496-119">**Item line 2:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="5a496-120">**Wiersz pozycji 3:** adres dostawy 2, TAN-ABCE12345B</span><span class="sxs-lookup"><span data-stu-id="5a496-120">**Item line 3:** Delivery address 2, TAN-ABCE12345B</span></span>
- <span data-ttu-id="5a496-121">**Wiersz pozycji 4:** adres dostawy 3, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="5a496-121">**Item line 4:** Delivery address 3, TAN-ABCD12345A</span></span>

<span data-ttu-id="5a496-122">W takim przypadku oryginalna faktura jest dzielona na dwie faktury i księgowana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="5a496-122">In this case, the original invoice is split into two invoices and posted in the following way:</span></span>

- <span data-ttu-id="5a496-123">Faktura 1 jest księgowana dla pozycji 1 i 2 pozycji, ponieważ oba wiersze mają ten sam adres dostawy i numer TAN.</span><span class="sxs-lookup"><span data-stu-id="5a496-123">Invoice 1 is posted for item line 1 and item line 2, because both lines have the same delivery address and TAN.</span></span>
- <span data-ttu-id="5a496-124">Faktura 2 jest księgowana dla wiersza 3.</span><span class="sxs-lookup"><span data-stu-id="5a496-124">Invoice 2 is posted for item line 3.</span></span>
- <span data-ttu-id="5a496-125">Faktura 3 jest księgowana dla wiersza 4.</span><span class="sxs-lookup"><span data-stu-id="5a496-125">Invoice 3 is posted for item line 4.</span></span>
