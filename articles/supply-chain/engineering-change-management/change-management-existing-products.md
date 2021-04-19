---
title: Włącz zarządzanie zmianami w istniejących produktach
description: W tym temacie opisano, jak włączyć zarządzanie zmianami istniejących produktów. Opisano w nim również przypadki, w których możliwość włączenia zarządzania zmianami jest ograniczona.
author: t-benebo
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: be7b17c1049f60379764c5424422ff1ac6ee1770
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830107"
---
# <a name="enable-change-management-on-existing-products"></a>Włącz zarządzanie zmianami w istniejących produktach

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, jak włączyć zarządzanie zmianami istniejących produktów. Opisano w nim również przypadki, w których możliwość włączenia zarządzania zmianami jest ograniczona.

Włączenie zarządzania zmianami istniejącego produktu umożliwia tworzenie wersji tego produktu oraz śledzenie zmian wprowadzonych w jego okresie użytkowania. W związku z tym zmiany te można śledzić przy użyciu zamówień zmian. Aby włączyć zarządzanie zmianami, należy przekonwertować odpowiednie produkty na *towary inżynieryjne* (zwane także produktami inżynieryjnymi). Produkty inżynieryjne to produkty, które są wersjonowane i zarządzane poprzez zarządzanie zmianami. Kreator jest dostarczany, aby poprowadzić Cię przez proces konwersji.

## <a name="turn-on-the-feature-in-your-system"></a>Włączanie funkcji w systemie

Aby skorzystać z tej możliwości, musisz wykonać następujące zadania:

1. Włącz funkcję zarządzania zmianami inżynierskimi i jej klucz konfiguracyjny zgodnie z opisem w [Omówienie zarządzania zmianami inżynieryjnymi](product-engineering-overview.md).
1. Włącz funkcję *Włącz zarządzanie zmianami w istniejących produktach* w zarządzaniu funkcjami. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="restrictions-and-limitations"></a>Ograniczenia i limity

Nie wszystkie typy produktów można przekonwertować na wszystkie inne typy. Obowiązują następujące ograniczenia i limity:

- Gdy produkt jest konwertowany na produkt inżynieryjny, pozostaje *produktem*. Nie stanie się on *produktem głównym*.
- Podczas konwertowania produktu głównego, który ma określony zestaw wymiarów, te wymiary są zachowywane po zmianie. Na przykład przekonwertowanie produktu głównego, który ma wymiar rozmiaru, spowoduje zachowanie wymiaru rozmiaru.

Jeśli więc istnieje odrębnych produktów, można go zmienić tylko na produkt inżynieryjny, który nie śledzi wymiaru produktu w transakcjach (tj. wymiar wersji nie jest używany). Zobacz pozostałe sekcje tego tematu, aby uzyskać więcej informacji na temat tych problemów.

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a>Przygotowanie do konwersji przez utworzenie wszystkich wymaganych kategorii produktów inżynieryjnych

*Kategoria produktów inżynieryjnych* musi być przypisana do każdego produktu inżynieryjnego. To przypisanie będzie można wykonać po uruchomieniu kreatora **Konwersji na produkt inżynieryjny**. Aby można było przekonwertować te produkty, musi *wcześniej* istnieć kategoria produktu inżynieryjnego dla odpowiednich produktów standardowych.

Kategoria produktu inżynieryjnego stanowi podstawę do utworzenia produktu inżynieryjnego i określa zestaw wartości domyślnych i zasad. Kategoria produktu inżynieryjnego musi odpowiadać produktowi, do którego ją przypisujesz. Na przykład typ produktu i grupa wymiarów muszą być zgodne zarówno z produktem, jak i z kategorią produktu inżynieryjnego. Aby uzyskać więcej informacji, zobacz [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).

> [!IMPORTANT]
> Kreator **Konwersji na produkt inżynieryjny** może konwertować produkt tylko na produkty inżynieryjne, w których ta wersja nie jest śledzona w transakcjach. Dlatego opcja **Wersja ścieżki w transakcjach** musi mieć wartość *Nie*, aby można było tworzyć kategorie produktów inżynieryjnych tworzyć w celu konwersji istniejących produktów.

Aby uzyskać więcej informacji na temat tworzenia kategorii produktów inżynieryjnych, zapoznaj się z tematem [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).

## <a name="run-the-convert-to-engineering-product-wizard"></a>Uruchamianie kreatora konwersji na produkt inżynieryjny

Kreator **Konwersji na produkt inżynieryjny** pomaga w konwertowaniu jednego lub większej liczby istniejących produktów na produkty inżynieryjne. Konwertuje produkty na produkty inżynieryjne (produkty w wersji), w których ta wersja nie jest śledzona w transakcjach (tj. wymiar wersji nie jest używany). Po zakończeniu konwersji można zarządzać produktami, używając funkcji zarządzania zmianami inżynieryjnymi.

Konwersja jest trwała. W związku z tym nie będzie można go później wycofać. 

Każdy przekonwertowany produkt inżynieryjny będzie nadal zwalniany w tych samych firmach, w których został wydany oryginalny produkt. Jednak inżynieryjna lista składowa BOM i trasy nie są automatycznie zwalniane do tych firm.

Aby uruchomić kreatora konwersji na produkt inżynieryjny i **Przekonwertować produkt na produkt inżynieryjny**, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. W siatce zaznacz pole wyboru dla każdego produktu, który chcesz przekonwertować.
1. W okienku akcji na karcie **Projekt** w grupie **Zarządzanie zmianami projektowymi** wybierz opcję **Konwertuj na produkt inżynieryjny**, aby otworzyć kreatora.
1. Pierwsza strona kreatora to strona **Powitania**. Jeśli nie znasz jeszcze procesu konwersji, przeczytaj uważnie informacje na tej stronie. Gdy wszystko będzie gotowe do kontynuacji, wybierz pozycję **Następny**.
1. Na stronie **Wybierz szczegóły dotyczące produktów**, które mają zostać przekonwertowane, są dostępne wszystkie wybrane produkty przed otwarciem kreatora. Sprawdź listę. Użyj przycisków **Nowy** i **Usuń** na pasku narzędzi, aby dodać lub usunąć produkty w razie konieczności.
1. W poniższych polach u góry siatki przypisz domyślne wartości do każdego produktu na liście. (Będziesz mógł zmienić te wartości dla poszczególnych produktów po zakończeniu konwersji). Wartości domyślne nie zostaną przypisane do produktów, do których została już przypisana odpowiednia wartość.

    - **Domyślna kategoria inżynieryjna** – Należy wybrać kategorię produktu inżynieryjnego, która zostanie przypisana do każdego produktu wymienionego na liście. Wybierana kategoria będzie stosowana tylko do produktów, które są z nim zgodne.
    - **Wersja domyślna** — wprowadź początkową wersję produktu, która ma zostać przypisana do każdego wyświetlanego produktu. Każdy produkt inżynieryjnych ma co najmniej jedną wersję inżynieryjną.
    - **Domyślny stan cyklu życia** — wybierz początkowy stan cyklu życia produktu, który ma zostać przypisany do każdego produktu wymienionego na liście.
    - **Bieżący BOM będzie częścią produktu inżynieryjnego** – To pole wyboru należy zaznaczyć, jeśli bieżący BOM dla każdego wymienionego produktu ma być używany jako BOM dla produktu inżynieryjnego.

    Aby uzyskać więcej informacji o ustawieniach produktu, zobacz następny krok.

1. Przejrzyj każdy produkt wymieniony w siatce i sprawdź, jak dobrze są stosowane do niego wartości domyślne. W przypadku każdego wiersza przejrzyj następujące informacje i ustaw odpowiednie pola:

    - **Numer produktu** – numer produktu.
    - **Nazwa produktu** – Nazwa produktu.
    - **Kategoria inżynieryjna** — umożliwia wybór kategorii produktów inżynieryjnych, do której po przekonwertowaniu produkt powinien należeć. Dla każdego produktu musi istnieć odpowiednia kategoria, co zostało opisane w poprzedniej sekcji tego tematu. Przypisz kategorię do każdego produktu.
    - **Wersja** — Wprowadź wersję produktu, która ma zostać przypisana do produktu po konwersji. Można na przykład wybrać liczbę, która będzie pasowała do sekwencji numerów używanej już w danej kategorii. Każda wersja inżynieryjna przechowuje dane techniczne, które są specyficzne dla tej wersji. Aby uzyskać więcej informacji, zobacz [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).
    - **Stan cyklu życia produktu** — wybierz stan cyklu życia produktu, w którym produkt powinien być po przekonwertowaniu. Stan cyklu życia produktu umożliwia kontrolowanie, które transakcje są dozwolone dla danej wersji inżynieryjnej. Aby uzyskać więcej informacji, zobacz [Stany cyklu życia produktu i transakcje](product-lifecycle-state-transactions.md).
    - **Ma BOM** — zaznaczone pole wyboru wskazuje, że produkt ma BOM. Ustawienie tego pola wyboru może pomóc w podjęciu decyzji, jak ustawić pole wyboru **Bieżący BOM będzie częścią produktu inżynieryjnego**.
    - **Bieżący BOM będzie częścią produktu inżynieryjnego** – To pole wyboru należy zaznaczyć, jeśli bieżący BOM dla produktu ma być używany jako BOM dla produktu inżynieryjnego. Tym BOM będzie zarządzać zarządzanie zmianami inżynieryjnymi. Jeśli produkt nie ma BOM lub chcesz później ręcznie utworzyć BOM dla przekonwertowanych produktów, wyczyść to pole wyboru.
    - **Zawiera błędy** — zaznaczone pole wyboru wskazuje, że konfiguracja produktu zawiera jeden lub więcej błędów. Na przykład typ produktu lub grupa wymiarów mogą nie odpowiadać kategorii. Produkty z błędami zostaną pominięte i nie zostaną przekonwertowane.

1. Po zakończeniu pracy wybierz pozycję **Weryfikuj** na pasku narzędzi, aby sprawdzić poprawność konfiguracji produktu. Dla każdego wiersza pole wyboru **Ma błędy** zostanie zaktualizowane, aby wskazać stan produktu. Dostosuj wartości, dopóki ustawienia każdego produktu nie będą wolne od błędów.
1. Gdy wszystkie produkty są poprawnie skonfigurowane, kliknij przycisk **Dalej**, aby kontynuować.
1. Strona **Potwierdź wybór** zawiera liczbę produktów, które nie mają błędów w konfiguracji i dlatego są gotowe do konwersji. Pokazuje także liczbę produktów, które zostaną pominięte z powodu błędów. Aby uruchomić konwersję jako zadanie wsadowe, ustaw opcję **Uruchom w partii** na wartość *Tak*.
1. Wybierz przycisk **Zakończ**, aby zastosować ustawienia i rozpocząć konwertowanie produktów na produkty inżynieryjne.

> [!NOTE]
> Jeśli system jest ustawiony do ręcznego akceptowania produktów przed ich zwolnieniem, trzeba zaakceptować każdy przekonwertowany produkt za pomocą strony **Otwórz wersje produktów** w odpowiednich firmach. Aby uzyskać więcej informacji, zobacz [Przejrzyj i zaakceptuj produkt przed jego zwolnieniem w firmie lokalnej](engineering-scenarios.md#accept).
