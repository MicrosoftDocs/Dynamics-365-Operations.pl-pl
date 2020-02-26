---
title: Metody płatności w biurach obsługi
description: W tym temacie opisano różne metody płatności, których można używać w biurze obsługi w programie Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRSalesTableOrderHistory, MCRCCAuthManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e7636f5c664634c680edf2ff9d8bae5ebb9035af
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023647"
---
# <a name="payment-methods-in-call-centers"></a>Metody płatności w biurach obsługi

[!include [banner](includes/banner.md)]

W programie Dynamics 365 Commerce konfiguracja kanału biura obsługi zawiera ustawienie o nazwie **Włącz kończenie zamówienia**. To ustawienie pomaga zagwarantować, że wszystkie zamówienia tworzone przez użytkowników kanału są zwalniane do przetwarzania zamówień tylko wtedy, gdy mają opłacone z góry lub wstępnie autoryzowane płatności mieszczące się w zatwierdzonych granicach tolerancji. Jeśli ustawienie **Włącz kończenie zamówienia** jest włączone, użytkownicy biura obsługi mogą wprowadzać płatności dla zamówień sprzedaży od odbiorców za pomocą funkcji przetwarzania płatności dostępnych w biurze obsługi. Jeśli ustawienie jest wyłączone, użytkownicy biura obsługi nie mogą korzystać z funkcji przetwarzania płatności zawartych w biurze obsługi, ale nadal mogą stosować przedpłaty do zamówień sprzedaży, używając do tego standardowych funkcji modułu Rozrachunki z odbiorcami.

W ramach konfiguracji kanału firma może zdefiniować metody płatności, które są dozwolone w kanale biura obsługi. Kanał biura obsługi używa tych samych metod płatności, jak zdefiniowane dla kanałów sklepu.

Aby skonfigurować metody płatności dla kanału biura obsługi, wybierz kolejno opcje **Handel detaliczny i inny** \> **Kanały** \> **Biura obsługi** \> **Wszystkie biura obsługi**, a następnie w menu **Konfiguracja** wybierz opcję **Metody płatności**.

Podczas tworzenia metody płatności istnieje pięć funkcji metod płatności, które można przypisać.

| Funkcja            | opis |
|---------------------|-------------|
| Normalny              | Użyj w metodzie płatności funkcji **Normalny** podczas definiowania metod płatności takich jak gotówka lub załączniki. Przy stosowaniu tego typu płatności dla zamówień sprzedaży w biurze obsługi, flaga **Przedpłata** jest domyślnie ustawiana na **Tak**. To zaksięguje natychmiast załącznik przedpłaty na koncie odbiorcy po przesłaniu tego zamówienia. Użytkownicy mogą zmienić flagę **Przedpłata** na **Nie** w razie potrzeby, tak aby załącznik płatności nie był tworzony do momentu księgowania faktury. Załącznik zaliczki jest księgowany w historii transakcji odbiorcy, gdzie zostanie systemowo rozliczony względem faktury dla zamówienia sprzedaży. |
| Sprawdzanie               | Użyj funkcji **Czek** podczas definiowania formy płatności w postaci czeku bankowego. Gdy ta forma płatności jest stosowana do zamówienia sprzedaży, użytkownik musi wprowadzić numer czeku odbiorcy w ramach przetwarzania zastosowania płatności. Płatności czekiem są zawsze traktowane jako przedpłaty w momencie zastosowania, a załączniki płatności są tworzone natychmiast po przesłaniu zamówienia. Te załączniki zaliczek będą systemowo rozliczane względem faktur tworzonych dla zamówienia. |
| Karty               | Typy płatności kartą reprezentują dowolny typ płatności, który wymaga wprowadzenia numeru karty zdefiniowanego na karcie płatniczej odbiorcy. Przykładami są karty kredytowe i karty upominkowe. Podczas konfigurowania tych typów płatności należy użyć menu **Ustawienia karty**, aby zdefiniować identyfikatory kart skojarzone z metodą płatności. Podczas wprowadzania zamówienia użytkownicy mogą wskazać, czy płatność kartą będzie dokonywana z góry, używając do tego opcji **Opłać z góry** widocznej na stronie wprowadzania płatności. Jeżeli działalność nie wymaga przedpłat, typowy przepływ pracy w faktycznej płatności kartą kredytową jest dwuetapowym procesem. Najpierw podczas wprowadzania zamówienia uzyskuje się autoryzację, a następnie podczas fakturowania płatność jest rozliczana i pobierana z karty odbiorcy. Dla płatności kartą upominkową zaleca się przedpłatę, ponieważ saldo na karcie upominkowej powinno zostać pomniejszone natychmiast, tak aby odbiorca nie mógł zastosować tej samej wartości w innym miejscu. |
| Odbiorca            | W funkcji **Odbiorca** w metodzie płatności istnieje domniemanie, że płatność zostanie zastosowana względem limitu kredytu odbiorcy lub dokonana „akonto”. W aplikacji Commerce odbiorcy można przypisać limit kredytu, który będzie weryfikowany podczas wprowadzania zamówienia. Płatności dokonane metodą płatności połączoną z funkcją **Odbiorca** tworzą zobowiązanie względem konta odbiorcy. Wtedy podczas fakturowania zamówienia jest wyświetlane saldo należne. W takich przypadkach odbiorcy zwykle wysyłają płatność zgodnie z ustalonymi warunkami. Alternatywnie w celu rozliczenia należnego salda można zastosować poprzedni otwarty załącznik kredytowy z konta odbiorcy. Należy zauważyć, że nawet po zdefiniowaniu tej metody płatności nie pojawia się ona wśród opcji płatności do wyboru w oknie wprowadzania zamówień w biurze obsługi, chyba że ustawisz flagę **Zezwalaj na akonto** w rekordzie odbiorcy, na którym aktualnie wykonujesz operacje. Ta flaga znajduje się na karcie **Ustawienia domyślne płatności** w rekordzie odbiorcy. |
| Usunięcie/zmiana środków płatniczych | Funkcja **Usunięcie/zmiana środków płatniczych** nie jest używana przez biuro obsługi. Stosuje się ją wyłącznie podczas definiowania metod płatności, których aplikacja punktu sprzedaży (POS) będzie używać w kanale sklepu. |

Podczas definiowania metod płatności należy je łączyć z kontem księgowym lub bankowym. Jeśli ten krok zostanie pominięty, użytkownicy będą widzieć błędy podczas prób zapisania typu płatności.

## <a name="refund-payment-methods"></a>Metody płatności zwrotów

W scenariuszach przetwarzania zwrotów biuro obsługi korzysta również z niektórych metod płatności zdefiniowanych w module Rozrachunki z odbiorcami. Aby skonfigurować te formy płatności, wybierz kolejno opcje **Handel detaliczny i inny** \> **Ustawienia kanału** \> **Ustawienia biura obsługi** \> **Metody zwrotu biura obsługi**. Należy wykonać tę konfigurację, aby przetwarzać czeki zwrotu do odbiorców. Na przykład jeśli odbiorca pierwotnie zapłacił za zamówienie gotówką lub czekiem, użytkownik może chcieć wysłać odbiorcy czek zwrotu za pośrednictwem modułu Rozrachunki z odbiorcami. W takim przypadku typy płatności gotówką i czekiem w biurze obsługi należy zamapować na poprawne metody płatności w module Rozrachunki z odbiorcami w celu zagwarantowania, że zwrot będzie poprawnie przetwarzany.

Ponadto jeśli użytkownik przetwarza zamówienie zwrotu jako użytkownik biura obsługi w aplikacji Commerce, ale nie jest w stanie połączyć zwrotu z pierwotną sprzedażą, należy zdefiniować metodę płatności **Zwrot** w parametrach biura obsługi. Wybierz kolejno opcje **Handel detaliczny i inny** \> **Ustawienia kanału** \> **Ustawienia biura obsługi** \> **Parametry biura obsługi**, a następnie na karcie **Autoryzacja zwrotu/zwrot** w polu **Metoda płatności** upewnij się, że jest zdefiniowana metoda płatności. Ustawiona tu metoda płatności będzie używana do obsługi zwrotów. Zazwyczaj będzie to metoda związana z czekiem lub kontem odbiorcy.
