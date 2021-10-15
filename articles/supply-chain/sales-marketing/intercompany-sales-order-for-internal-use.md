---
title: Tworzenie międzyfirmowego zamówienia sprzedaży do użytku wewnętrznego
description: W tym temacie wyjaśniono, jak utworzyć międzyfirmowe zamówienie sprzedaży do użytku wewnętrznego
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0718a1560ec42df2a0a12e8b81484aa3be46d2d8
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548466"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>Tworzenie międzyfirmowego zamówienia sprzedaży do użytku wewnętrznego

[!include [banner](../../includes/banner.md)]

Zazwyczaj międzyfirmowe zamówienie sprzedaży jest tworzone automatycznie na podstawie międzyfirmowego zamówienia zakupu. Można również ręcznie utworzyć międzyfirmowe zamówienie sprzedaży, które następnie wygeneruje międzyfirmowe zamówienie zakupu w firmie międzyfirmowej odbiorcy.

![Wewnętrzny proces sprzedaży międzyfirmowej](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>Ręczne tworzenie międzyfirmowego zamówienia sprzedaży

Wykonaj poniższe kroki w firmie B, jak pokazano na ilustracji.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Zamówienia sprzedaży**, aby utworzyć zamówienie sprzedaży.
1. Na **stronie Tworzenie zamówienia sprzedaży** wybierz konto odbiorcy. Upewnij się, że na skróconej karcie **Ogólne** jest zaznaczone pole wyboru **Międzyfirmowe**. Wskazuje to, że wybrany odbiorca jest klientem międzyfirmowym.
1. Wprowadź lub zmodyfikuj informacje, wybierz **OK**, a następnie uzupełnij wiersze zamówienia jak zwykle.

    Wartość **pola Adres dostawy** jest kopiowana z nagłówka międzyfirmowe zamówienie sprzedaży do międzyfirmowe zamówienie zakupu dostawy. Wartość **pola Kod towaru**, w tym wymiarów produktu, oraz wartości pól **Data dostawy** i **Kod waluty** są kopiowane z wierszy międzyfirmowe zamówienie sprzedaży do międzyfirmowe zamówienie zakupu dostawy.

1. W nagłówku zamówienia kliknij opcję **Międzyfirmowe**, aby wyświetlić odpowiednie międzyfirmowe zamówienie zakupu.
1. W wierszach zamówienia wybierz opcję **Międzyfirmowe**, aby wyświetlić informacje o dostępnych zapasach w handlu międzyfirmowym.

> [!TIP]
> Międzyfirmowe zamówienia sprzedaży można wyświetlić na stronie **Zamówienia międzyfirmowe**.

> [!NOTE]
> Zaleca się, aby podczas pracy z zamówieniami międzyfirmymi wyczyścić pole wyboru **Usuń zamówienie po zafakturowaniach** na stronie **Parametry rozrachunków z odbiorcami**. W przeciwnym razie powiązane zamówienie zakupu zostanie usunięte. Zalecamy też wyczyszczenie pola wyboru **Usuń zamówienie zakupu po zafakturowaniu** na stronie **Parametry kont do zapłaty**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
