---
title: Konwencje
description: W tym temacie opisano, jak skonfigurować konwencje w celu ustalenia sposobu rozliczania kosztów w programie w Globalnym księgowaniu zapasów.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2d629b082b423edf417714b8362be3364bc861e78f62d430a4d7083b8c49611a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773424"
---
# <a name="conventions"></a>Konwencje

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Konwencja jest pojemnikiem dla zestawu zasad, które wpływają na zachowanie systemu. W oparciu o wymagania biznesowe należy określić konwencje, stosując kombinację różnych zasad, które określają sposób księgowania kosztów w Globalnym księgowaniu zapasów. Każdą konwencję można powiązać z jedną lub kilkoma księgami, aby zapewnić spójność zasad rachunkowości stosowanych w poszczególnych księgach.

Aby skonfigurować konwencje, przejdź do menu **Globalne księgowania zapasów\> Konfiguracja \> Konwencje**. Dla każdej konwencji ustaw następujące pola:

- **Nazwa** — Wprowadź nazwę konwencji.
- **Opis** – wprowadź opis konwencji.
- **Koszt Polityka obiektowa** — umożliwia wybór zasad obiektów kosztów. Zasady te określają poziom szczegółowości, jaki system stosuje przy obliczaniu i utrzymywaniu wartości zapasów. Dostępne są następujące predefiniowane opcje:

    - Produkt
    - Produkt — miejsce
    - Produkt — Miejsce — Magazyn

    Na przykład w przypadku wybrania opcji *Produkt — Miejsce* dla każdego ruchu magazynowego (wypływu lub wpływu) system oblicza i obsługuje koszt magazynowy każdego produktu na poziomie lokacji. W związku z tym ruchy zapasów na niższych poziomach, takich jak poziom magazynu, nie mają wpływu na wartość zapasów. (Przykładem przeniesienia na poziomie magazynu jest przeniesienie pozycji pomiędzy dwoma magazynami w jednym miejscu). Podobnie nie można wyświetlić kosztu zapasów na niższym poziomie, np. na poziomie magazynu.

- **Polityka podstawy pomiaru danych wejściowych** – Wybierz politykę podstawy pomiaru danych wejściowych. Zasady te określają koszty, które powinny wpłynąć na konto zapasów oraz koszty, które powinny zostać obciążone. Poniższe opcje są istotne dla firm handlowych:

    - **Normalna historyczna** – Wszystkie składniki kosztów wpływają na konto zapasów.
    - **Standard** – koszt standardowy wpływa na konta zapasów, a różnica pomiędzy kosztem stosowanym a rzeczywistym obciąża konta odchyleń. Jeśli chcesz stworzyć politykę *Standard* podstawy wyceny wejścia, musisz najpierw stworzyć cennik, z którego polityka będzie mogła wyszukać standardowy koszt pozycji.
    - **Cenniki** – Globalne księgowanie zapasów umożliwia pobieranie cen towarów z wielu firm. Można zdefiniować cennik, z którego będą korzystać zasady podstawy wyceny danych wejściowych. W ten sposób system wie, gdzie należy sprawdzić cenę towaru. Wykonaj poniższe kroki, aby skonfigurować cenniki:

        1. W polu **Nazwa** wprowadź nazwę.
        1. W polu **Opis wprowadź** opis.
        1. W polu **Typ wyceny** wybierz typ wyceny (*Koszt standardowy* lub *Koszt planowany*).
        1. W polu **Typ ceny** wybierz typ ceny (*Koszt*, *Zakup* lub *Cena sprzedaży*).
        1. Dodaj wersję wyceny.
        1. W okienku akcji wybierz pozycję **Cena**, aby sprawdzić poprawność cen towarów na cenniku.

- **Zasada założeń przepływu kosztów** – wybierz zasady założeń przepływu kosztów. Zasady te określają sposób, w jaki koszty są usuwane z magazynu i zgłaszane jako koszt własny sprzedaży. Dostępne są następujące predefiniowane opcje:

    - Średnia
    - Określony — partia

    > [!NOTE]
    > Globalne księgowanie zapasów to system inwentaryzacji ciągłej. W związku z tym system śledzi wartość zapasów według transakcji.

- **Zasady dotyczące elementów kosztów** — można definiować zasady dotyczące elementów kosztów i łączyć je z tym polem. *Element kosztów* to koszt zasobu zużywanego przez zdarzenie. Elementów kosztów można używać do śledzenia i kategoryzacji kosztów. Aby utworzyć zasady dotyczące elementów kosztów, wprowadź informacje w następujących miejscach:

    - Pole **Nazwa**
    - Pole **Opis**
    - Lista **Składników kosztów**
    - Siatka **reguł**

    Jeśli nie chcesz dalej rozbijać wartości zapasów, musisz utworzyć listę elementów kosztu, która ma jeden element kosztu. Następnie należy utworzyć politykę elementu kosztu, aby zmapować wszystkie odpowiednie typy pomiaru (składniki kosztu) do tego elementu kosztu.
