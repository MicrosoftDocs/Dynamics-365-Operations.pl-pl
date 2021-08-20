---
title: Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych
description: W tym temacie opisano sposób tworzenia skoroszytu programu Excel w celu umożliwienia edycji transakcji detalicznych w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: bfc3f6898087445e0276994ceeb52c178785bf3604fa163939327e99a0564f64
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753115"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia skoroszytu programu Excel w celu umożliwienia edycji transakcji detalicznych w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Dostępny jest wstępnie zdefiniowany szablon programu Excel, do którego odbiorcy mogą uzyskiwać dostęp z różnych części systemu i którego mogą używać do edytowania transakcji sprzedaży detalicznej i przeprowadzania ich inspekcji. Odbiorcy mogą również utworzyć niestandardowy skoroszyt programu Excel, którego będzie można użyć we wspomnianych celach.

## <a name="create-and-configure-an-excel-workbook"></a>Tworzenie i konfigurowanie skoroszytu programu Excel

Aby utworzyć i skonfigurować skoroszyt programu Excel, by móc edytować transakcje sprzedaży detalicznej, wykonaj kroki opisane poniżej.

1. Otwórz program Excel i utwórz pusty skoroszyt.
1. Na karcie **Wstawianie** wybierz pozycję **Moje dodatki**.
1. W prawym okienku wybierz łącze **Dodaj informacje dotyczące serwera**.
1. Wprowadź adres URL serwera, a następnie wybierz opcję **OK**.
1. Jeśli zostanie wyświetlony komunikat o błędzie „Nie znaleziono rejestracji apletów”, w celu rozwiązania problemu należy wykonać następujące kroki:

    1. W rozwiązaniu Commerce wybierz kolejno opcje **Administrowanie systemem \> Konfiguracja \> Parametry aplikacji pakietu Office**.
    1. Na skróconej karcie **Parametry aplikacji** wybierz opcję **Zainicjuj parametry aplikacji**.
    1. W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **OK**.
    1. Na skróconej karcie **Zarejestrowane aplety** wybierz opcję **Zainicjuj rejestrację apletu**.
    1. W razie potrzeby powtórz trzy poprzednie kroki.

1. Wybierz opcję **Projekt**, a następnie wybierz opcję **Dodaj tabelę**.
1. W zależności od danych, które mają zostać zmodyfikowane, należy wybrać jednostki, które muszą zostać dodane do skoroszytu programu Excel na potrzeby edycji. Dla ułatwienia można skorzystać z poniższej tabeli.

    | Typ transakcji | Jednostki danych, których należy użyć |
    |------------------|----------------------|
    | Transakcje kasowe i przeniesienia, zamówienia online, asynchroniczne zamówienia odbiorcy, asynchroniczne zapytania ofertowe odbiorcy | Transakcja (podlegająca inspekcji), transakcja sprzedaży (podlegająca inspekcji), transakcje płatności (podlegające inspekcji), transakcje podatku (podlegające inspekcji), transakcje rabatu (podlegające inspekcji), transakcje opłat (podlegające inspekcji) |
    | Przekazanie pieniędzy do banku | Transakcja (podlegająca inspekcji), transakcje wpłat bankowych (podlegające inspekcji) |
    | Przekazanie pieniędzy do sejfu | Transakcja (podlegająca inspekcji), transakcje wpływające na kwotę w kasecie kasowej (podlegające inspekcji) |
    | Deklaracja środków płatniczych | Transakcja (podlegająca inspekcji), transakcje deklaracji środków płatniczych (podlegające inspekcji) |
    | Przychód, wydatek | Transakcja (podlegająca inspekcji), transakcje przychodów/wydatków (podlegające inspekcji), transakcje płatności (podlegające inspekcji) |
    | Deklaracja kwoty początkowej, pobranie środków płatniczych, przyjęcie do kasy, reszta dla metody płatności, płatność faktury, kaucja odbiorcy | Transakcja (podlegająca inspekcji), transakcje płatności (podlegające inspekcji) |

    > [!NOTE]
    > Ważne jest, aby do każdego skoroszytu programu Excel dodać tylko jedną jednostkę danych. Ponadto wszystkie pola oznaczone symbolem klucza muszą zostać dodane do odpowiedniego skoroszytu.

1. Po skonfigurowaniu skoroszytu zastosuj wymagane filtry. Należy pamiętać o zastosowaniu tych samych filtrów do wszystkich arkuszy w pliku. Należy unikać ładowania bardzo dużych ilości danych do pliku programu Excel. Mogłoby to negatywnie wpłynąć na wydajność oraz spowolnić działanie programu Excel i systemu. Zaleca się, aby w pliku były zawsze stosowane filtry „Firma” oraz „Numer zestawienia” lub „Numer transakcji”.
1. Po skonfigurowaniu filtrów wybierz opcję **Odśwież**, aby załadować dane.
1. Edytuj wymagane dane, a następnie opublikuj je. Jeśli przycisk **Publikuj** jest niedostępny, oznacza to, że niektóre pola kluczy prawdopodobnie nie zostały dodane do skoroszytu programu Excel.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką](edit-cash-trans.md)

[Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy](edit-order-trans.md)

[Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej](edit-financial-dim.md)

[Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]