---
title: Globalna potrącona zaliczka na podatek
description: Ten temat zawiera informacje dotyczące globalnej funkcjonalności potrąconej zaliczki na podatek oraz sposobu jej skonfigurowania. Funkcjonalność globalnego podatku potrącanego u źródła została rozszerzona o transakcje z dostawcą i odbiorcą, dzięki czemu zaliczka na podatek jest obliczany na poziomie towaru.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 17ed1dcae97f6cd28175c483be5ca3ce96d59e05
ms.sourcegitcommit: 053f4cda6862fbcd9e3aa6e9cb009e7de833beac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/28/2021
ms.locfileid: "5075745"
---
# <a name="global-withholding-tax"></a><span data-ttu-id="80c3e-104">Globalna potrącona zaliczka na podatek</span><span class="sxs-lookup"><span data-stu-id="80c3e-104">Global withholding tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80c3e-105">Ten temat zawiera informacje dotyczące globalnej funkcjonalności potrąconej zaliczki na podatek oraz sposobu jej skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="80c3e-105">This topic provides information about global withholding tax functionality and explains how to set it up.</span></span> <span data-ttu-id="80c3e-106">Nowa funkcja jest dostępna w wersjach 10.0.17 i późniejszych.</span><span class="sxs-lookup"><span data-stu-id="80c3e-106">The new functionality is available in version 10.0.17 and later.</span></span>

<span data-ttu-id="80c3e-107">Funkcjonalność globalnego podatku potrącanego u źródła została rozszerzona o transakcje z dostawcą i odbiorcą, dzięki czemu zaliczka na podatek jest obliczany na poziomie towaru.</span><span class="sxs-lookup"><span data-stu-id="80c3e-107">Global withholding tax functionality is enhanced for vendor and customer transactions, so that withholding tax is calculated at the item level.</span></span> <span data-ttu-id="80c3e-108">Saldo na rachunku zaliczki na podatek z transakcji zakupu można rozliczyć, uruchamiając zlecenie zapłaty podatku u źródła na rachunku rozliczenia potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="80c3e-108">The balance in the withholding tax account from purchase transactions can be settled by running the withholding tax payment job against the withholding tax settlement account.</span></span>

> [!NOTE]
> <span data-ttu-id="80c3e-109">Globalna potrącona zaliczka na podatek nie obsługuje funkcji **Obsługa opłat** na stronach zamówienia zakupu, faktury od dostawcy i zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="80c3e-109">Global withholding tax doesn't support the **Maintain charges** function on the purchase order, vendor invoice, and sales order pages.</span></span>

## <a name="turn-on-global-withholding-tax"></a><span data-ttu-id="80c3e-110">Włączanie globalnego potrącania zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="80c3e-110">Turn on global withholding tax</span></span>

1. <span data-ttu-id="80c3e-111">W obszarze roboczym **Zarządzanie funkcjami** wybierz z listy **Globalne potrącanie zaliczki na podatek**, a następnie wybierz pozycję **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="80c3e-111">In the **Feature management** workspace, select **Global withholding tax**, and then select **Enable now**.</span></span>
2. <span data-ttu-id="80c3e-112">Przejdź do **Podatek \> Konfiguracja \> Parametry \> Parametry księgi głównej**, a następnie na karcie **Potrącona zaliczka na podatek** ustaw opcję **Włącz globalną potrącanie zaliczki na podatek** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="80c3e-112">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Withholding tax** tab, set the **Enable global withholding tax** option to **Yes**.</span></span>
3. <span data-ttu-id="80c3e-113">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="80c3e-113">Select **Save**.</span></span>
4. <span data-ttu-id="80c3e-114">Odśwież stronę w przeglądarce sieci web.</span><span class="sxs-lookup"><span data-stu-id="80c3e-114">Refresh the page in your web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="80c3e-115">Nie można włączona funkcja globalnej potrąconej zaliczki na podatek w przypadku krajów/regionów, w których istnieją już zlokalizowane rozwiązania dotyczące potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="80c3e-115">Global withholding tax functionality can’t be turned on for countries/regions where localized withholding tax solutions already exist.</span></span> <span data-ttu-id="80c3e-116">To m.in. Indie, Brazylia, Tajlandia, Arabia Saudyjska, Irlandia, Wielka Brytania i Stany Zjednoczone.</span><span class="sxs-lookup"><span data-stu-id="80c3e-116">These areas include but are not restricted to India, Brazil, Thailand, Saudi Arabia, Ireland, Great Britain and the United States.</span></span>