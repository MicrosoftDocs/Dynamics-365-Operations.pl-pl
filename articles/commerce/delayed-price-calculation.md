---
title: Opóźnienie dokładnych obliczeń cen i rabatów w celu poprawy wydajności
description: W tym artykule opisano możliwości opóźnienia obliczania cen, która jest dostępna w punkcie sprzedaży i biurze obsługi rozwiązania Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 09/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 6926c288a91dbe66b6ffc2e6c06f866d3ebd7652
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845904"
---
# <a name="delay-exact-price-and-discount-calculation-for-improved-performance"></a>Opóźnienie dokładnych obliczeń cen i rabatów w celu poprawy wydajności

[!include [banner](includes/banner.md)]

W tym artykule opisano możliwości opóźnienia obliczania cen, która jest dostępna w punkcie sprzedaży i biurze obsługi rozwiązania Microsoft Dynamics 365 Commerce.

Rozwiązanie Dynamics 365 Commerce umożliwia tworzenie rabatów wielowymiarowych stosowanych w przypadku, gdy jest połączonych wiele wierszy zamówienia sprzedaży lub oferty sprzedaży. Te rabaty obejmują rabaty łączone, próg oraz rabaty ilościowe.

Po każdym dodaniu nowego wiersza do zamówienia aparat wyceny rozwiązania Commerce ocenia cały koszyk w celu ustalenia, czy może zostać zastosowany któryś z tych wielowymiarowych rabatów. Z powodu ponownego obliczania dodanie nowych wierszy może wpłynąć na wydajność w miarę wzrostu zamówienia sprzedaży.

Jednak firmy B2B i niektóre firmy B2C często mają zamówienia dużych rozmiarów. W związku z tym czas oczekiwania na ponowne obliczanie przez aparat cen po dodaniu każdego towaru do koszyka może być czasochłonne. Ponadto w przypadku dużych zamówień zazwyczaj nie jest ważne, aby przy każdym dodaniu towaru do koszyka była wyświetlana dokładna cena i rabat. Ważne jest, aby użytkownicy mogli szybko dodawać towary. Możliwość opóźnienia obliczania dokładnych cen i rabatów, dopóki użytkownik tego nie zażąda lub do czasu sfinalizowania zamówienia, może znacznie poprawić wydajność. Może także skrócić czas wymagany do zakończenia składania zamówienia.

Możliwość opóźnienia dokładnych obliczeń cen i rabatów jest od dłuższego czasu dostępna w punkcie sprzedaży. W wersji Commerce 10.0.22 jest ona dostępna również dla biur obsługi.

## <a name="enable-delayed-price-and-discount-calculation-for-pos"></a>Włączanie opóźnionego obliczania cen i rabatów dla punktów sprzedaży

Aby włączyć opóźnione obliczanie cen i rabatów dla punktów sprzedaży, postępuj zgodnie z tymi krokami.

1. W centrali rozwiązania Commerce przejdź do profilu funkcji skojarzonego z fizycznym sklepem.
1. Na skróconej karcie **Kwota** włącz konfigurację **Ręczne obliczanie rabatów dla wielu towarów**.
1. Otwórz konstruktora układu ekranu dla kas, dla których ma być włączone opóźnienie obliczania.
1. Dodaj przycisk dla operacji **Oblicz sumę** do żądanej siatki przycisków.
1. Uruchom zadania **1070** i **1090**.

Teraz, gdy towary są dodawane do transakcji, rabaty te nie są obliczane, chyba że kasjer wybierze przycisk **Oblicz sumę**. Po wybraniu opcji **Oblicz sumę** dla transakcji zawsze obliczane będą rabaty wielowymiarowe. Kasjer nie będzie musiał ponownie wybrać tego przycisku, nawet jeśli do koszyka dodano dodatkowe towary. System nie pozwoli kasjerowi na przechwycenie płatności, dopóki nie zostanie wybrana opcja **Oblicz sumę**.

## <a name="enable-delayed-price-and-discount-calculation-for-call-center"></a>Włączanie opóźnionego obliczania cen i rabatów dla biur obsługi

Aby włączyć opóźnione obliczanie cen i rabatów dla biur obsługi, postępuj zgodnie z tymi krokami.

1. W centrali rozwiązania Commerce przejdź do opcji **Obszar roboczy \> Zarządzanie funkcjami**.
1. Włącz funkcję **Zapobiegaj nieumyślnemu obliczaniu ceny dla zamówień handlowych**. Ta funkcja jest niezbędnym wymaganiem wstępnym do obsługi możliwości opóźnionego obliczania cen i rabatów.

    > [!NOTE]
    > W przypadku nowych wdrożeń domyślnie jest włączona funkcja **Zapobiegaj nieumyślnemu obliczaniu ceny dla zamówień handlowych**.

1. Przejdź do opcji **Parametry rozwiązania Commerce \> Ceny i rabaty**.
1. W sekcji **Różne** włącz konfigurację **Ręczne obliczanie cen i rabatów wielowierszowych**.

Teraz, gdy w biurze obsługi jest tworzone lub edytowane zamówienie sprzedaży lub oferta sprzedaży, dokładne obliczenie ceny i rabatu dla tej oferty zostanie opóźnione. Aparat cen będzie uwzględniał tylko dodawany lub edytowany wiersz sprzedaży i zignoruje wszystkie inne wiersze sprzedaży. Kwota netto towaru uwzględnia obliczanie ceny i proste rabaty (procent rabatu lub kwota rabatu od pojedynczego towaru). Jednakże rabaty łączone, progowe i ilościowe nie będą stosowane. Użytkownicy biura obsługi, którzy chcą wyświetlić dokładną cenę z uwzględnieniem wszystkich rabatów, mogą wybrać jeden z trzech przycisków: **Ponowne obliczanie**, **Sumy** lub **Zakończ**.

> [!NOTE]
> W przypadku zamówień biur obsługi system wyświetla komunikat ostrzegawczy, przypominając użytkownikowi, że musi wybrać przycisk **Oblicz ponownie**, **Sumy** lub **Zakończ**, aby dokładnie określić ceny i rabaty do wykonania. W przypadku zamówień, w których dostępny jest przycisk **Zakończ**, użytkownik biura obsługi nie może pominąć dokładnego obliczania ceny i rabatu, ponieważ musi wybrać opcję **Zakończ**, aby zakończyć przechwytywanie zamówienia. W przypadku zamówień, w których przycisk **Zakończ** jest niedostępny, nie ma akcji wskazującej zakończenie przechwytywania zamówienia. Dlatego użytkownik biura obsługi jest odpowiedzialny za wybranie opcji **Oblicz ponownie** lub **Sumy** przed zakończeniem przechwytywania zamówienia.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
