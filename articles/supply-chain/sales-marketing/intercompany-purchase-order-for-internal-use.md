---
title: Tworzenie i fakturowanie międzyfirmowego zamówienia zakupu do użytku wewnętrznego
description: W tym artykule wyjaśniono, jak utworzyć i zafakturować międzyfirmowe zamówienie zakupu do użytku wewnętrznego
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 2260128c276ab7b712f7c97945b188ea42099fb4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877545"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>Tworzenie i fakturowanie międzyfirmowego zamówienia zakupu do użytku wewnętrznego

[!include [banner](../../includes/banner.md)]

Możesz utworzyć międzyfirmowe zamówienie zakupu dla dostawcy międzyfirmowego. Spowoduje to automatyczne utworzenie międzyfirmowego zamówienia sprzedaży u dostawcy międzyfirmowego.

![Wewnętrzny proces zakupów międzyfirmowych](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>Utwórz międzyfirmowe zamówienie zakupu i odpowiadające mu międzyfirmowe zamówienie sprzedaży

Wykonaj poniższe kroki w firmie AAA, jak pokazano na ilustracji.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Zamówienia zakupu** \> **Wszystkie zamówienia zakupu**.
1. Na stronie listy **Wszystkie zamówienia zakupu** utwórz zamówienie zakupu dla dostawcy międzyfirmowego. Wartości pól są kopiowane z konta dostawcy do zamówienia zakupu.

    Ponieważ pracujesz z dostawcą międzyfirmowym, w firmie odpowiadającej dostawcy jest tworzone międzyfirmowe zamówienie sprzedaży. Numer międzyfirmowego zamówienia sprzedaży może być taki sam jak numer międzyfirmowego zamówienia zakupu i może zawierać identyfikator firmy. Struktura używanej numeracji zależy od wyboru dokonanego w polu **Numerowanie zamówień sprzedaży** na stronie **Międzyfirmowe**. Na przykład jeśli tworzysz zamówienie zakupu 00029\_064 w firmie AAA, numer zamówienia sprzedaży w firmie BBB to AAA00029\_64.

    Komunikat informacyjny informuje, że utworzono międzyfirmowe zamówienie zakupu i międzyfirmowe zamówienie sprzedaży. Komunikat zawiera informacyjnie numer międzyfirmowego zamówienia sprzedaży.

1. Dodaj towary w wierszu do zamówienia zakupu. Odpowiednie pozycje są automatycznie dodawane do międzyfirmowego zamówienia sprzedaży. Jeśli element nie istnieje w innej firmie, pojawi się komunikat i nie można dodać towaru do zamówienia zakupu. Aby rozwiązać ten problem, przełącz się na inną firmę i zwolnij produkt do tej firmy. Element będzie dostępny i będzie mógł być dodawany do zamówień sprzedaży w tej firmie. Następnie należy wrócić do firmy od zamówienia zakupu i kontynuować dodawanie towarów w wierszu.
1. Po zakończeniu wprowadzania informacji dotyczących zamówienia zakupu, należy je potwierdzić.

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>Przetwarzanie międzyfirmowego dokumentu dostawy i faktury dla odbiorcy

Wykonaj poniższe kroki w firmie BBB, jak pokazano na ilustracji.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wróć do strony **Wszystkie zamówienia sprzedaży** i wybierz międzyfirmowe zamówienie sprzedaży.
1. W okienku akcji wybierz kartę **Pobrania i pakowania**, a następnie **wybierz pozycję Dokument dostawy**.
1. Zaznacz pole wyboru **Księgowanie**.
1. Kliknij przycisk **OK**. Dokument dostawy jest księgowany w firmie BBB.
1. Wróć do strony **Wszystkie zamówienia sprzedaży** i wybierz międzyfirmowe zamówienie sprzedaży.
1. W okienku akcji wybierz kartę **Faktura**, a następnie ponownie wybierz opcję **Faktura**.
1. Zaznacz pole wyboru **Księgowanie**.
1. Kliknij przycisk **OK**.

    Faktura dla odbiorcy dla międzyfirmowego zamówienia sprzedaży jest księgowana w firmie BBB.

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>Przetwarzanie międzyfirmowego dokumentu przyjęcia produktów i faktury dla dostawcy

Wykonaj poniższe kroki w firmie AAA, jak pokazano na ilustracji.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Wróć do strony **Wszystkie zamówienia zakupu** i wybierz międzyfirmowe zamówienie zakupu.
1. W okienku akcji wybierz kartę **Dostarczone**, a następnie ponownie wybierz opcję **Dokument przyjęcia produktów**. Zostaje utworzony dokument przyjęcia produktów. Numer przyjęcia produktu jest taki sam jak numer międzyfirmowego dokumentu dostawy.
1. Zaznacz pole wyboru **Księgowanie**.
1. Kliknij przycisk **OK**.
1. Wróć do strony **Wszystkie zamówienia zakupu** i wybierz międzyfirmowe zamówienie zakupu.
1. W okienku akcji wybierz opcję **Faktura**, a następnie ponownie wybierz opcję **Faktura**. Zostanie wówczas utworzona faktura dostawcy. Numer faktury od dostawcy jest taki sam jak numer faktury odbiorcy międzyfirmowego.
1. Zakończ wprowadzanie faktury od dostawcy, a następnie zaksięguj ją.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
