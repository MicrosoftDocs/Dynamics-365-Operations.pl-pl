---
title: Tworzenie zamówień dla biur obsługi
description: W tym artykule opisano przykładową procedurę, w której użytkownik call center wyszukuje klienta, tworzy nowe zamówienie, wyszukuje produkt i pobiera płatność od klienta w Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 08/05/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16d483896ce131e9a7bc60ab5ea7b8fa01a3bea8
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228518"
---
# <a name="create-call-center-orders"></a>Tworzenie zamówień dla biur obsługi

[!include [banner](../includes/banner.md)]

W tym artykule opisano przykładową procedurę, w której użytkownik call center wyszukuje klienta, tworzy nowe zamówienie, wyszukuje produkt i pobiera płatność od klienta w Microsoft Dynamics 365 Commerce. Procedura wykorzystuje dane firmy demonstracyjnej USRT i jest przeznaczona dla pracowników zamówień sprzedaży. 

## <a name="prerequisites"></a>Wymagania wstępne

Użytkownik, który zakończy procedurę, musi być skonfigurowany jako użytkownik call center. Opcjonalnie można opublikować półroczny katalog Fabrikam z co najmniej jednym kodem źródłowym.

### <a name="add-yourself-as-a-call-center-user"></a>Dodaj siebie jako użytkownika call center

Aby dodać siebie jako użytkownika call center, wykonaj następujące kroki.

1. W centrali Commerce headquarters przejdź do **Handel detaliczny i inny \> Kanały \> Biura obsługi \> Wszystkie biura obsługi**.
1. W polu **Użytkownicy** wybierz pozycję **Użytkownicy kanału**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Identyfikatora użytkownika** wprowadź swój identyfikator użytkownika.
1. Następnie w polu **Nazwa** nadaj nazwę użytkownika. Nazwa użytkownika może być taka sama jak identyfikator użytkownika.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Biura obsługi \> Wszystkie biura obsługi**.
1. Wybierz identyfikator kanału sprzedaży dla call center.
1. Potwierdź, że opcja **Włącz zakończenie zamówienia** ma wartość **Tak**. Jeśli ta opcja nie jest widoczna, możesz pominąć ten krok.

## <a name="complete-the-example-call-center-procedure"></a>Wykonaj przykładową procedurę dla centrum obsługi

Aby wykonać przykładową procedurę dla centrum obsługi, wykonaj następujące czynności.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Odbiorcy \> Obsługa klienta**.
1. Na karcie **Wyszukiwanie klientów** wprowadź kryteria wyszukiwania, aby wyszukać klienta. W tej przykładowej procedurze wpisz **Karen**.
1. Wybierz opcję **Wyszukaj**. Zostanie wyświetlone okno dialogowe **Wyszukiwanie odbiorcy** i zostanie wyświetlona lista wyników wyszukiwania.
1. Wybierz rekord klienta dla **Karen Berg**, który ma numer konta klienta **2001**, a następnie wybierz **Wybierz**.
1. W okienku akcji kliknij pozycję **Nowe zamówienie sprzedaży**.
1. Po prawej stronie wybierz kartę **Nagłówek**.
1. Na skróconej karcie **Dostawa** w polu **Tryb dostawy** wybierz pozycję **Standard 99**.

    ![Wybór sposobu dostawy.](../media/Select_Mode_of_Delivery.png)

1. Po prawej stronie wybierz kartę **Wiersze**.
1. W sekcji **Wiersze zamówienia** sprzedaży w nowym wierszu sprzedaży w polu **Numer towaru** wprowadź kod towaru, który ma być wyszukiwany. W tym przykładzie należy wprowadzić **wartość 81327**, a następnie wybrać produkt z listy rozwijanej w celu dodania go do zamówienia sprzedaży.
1. W polu **Ilość** wprowadź ilość sprzedaży.
1. W polu **Źródło kodu** wybierz kod źródłowy katalogu. Jeśli nie ma żadnych aktywnych kodów źródłowych, można pominąć ten krok.
1. W okienku akcji wybierz **Gotowe**, aby zarejestrować informacje o płatności od odbiorcy. Ta akcja spowoduje otwarcie okna dialogowego **Podsumowania zamówienia sprzedaży**, w którym jest pokazywana łączna należna kwota. Akcja wyzwala również obliczanie opłat, takich jak wysyłka i obsługa, i wyświetla je w oknie dialogowym **Podsumowania zamówienia sprzedaży**.

    ![Przycisk Wykonaj.](../media/Complete_button.png)

1. W polu dialogowym **Podsumowanie zamówienia sprzedaży**, na karcie **Płatności** wybierz przycisk **Dodaj**, aby przechwycić płatności.

    ![Okno dialogowe Podsumowanie zamówienia sprzedaży.](../media/order_summary.png)

1. W oknie dialogowym **Wprowadzanie informacji o płatności** odbiorcy w polu **Metoda płatności** wybierz metodę płatności. W tym przykładzie wybierz wartość **Gotówka**.
1. W polu **Kwota płatności** wprowadź kwotę płatności. W tym przykładzie należy wprowadzić **wartość 120,00**, która jest równa saldu zamówienia wyświetlanego w oknie dialogowym **Podsumowania zamówienia sprzedaży**. Wpisując tę kwotę, możesz zrealizować zamówienie jako w pełni opłacone.
1. Kliknij przycisk **OK**.
1. Wybierz opcję **Prześlij**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy](../customize-email-delivery-mode.md)

[Zmienianie metody dostawy w punkcie sprzedaży](../pos-change-delivery-mode.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
