---
title: Książki adresowe — często zadawane pytania
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące książek adresowych.
author: msftbrking
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 922900b20b878dd8b479158d47a9f7792caa684d
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796905"
---
# <a name="address-books-faq"></a>Książki adresowe — często zadawane pytania

[!include [banner](../includes/banner.md)]

## <a name="how-do-i-check-for-duplicate-records"></a>Jak sprawdzić, czy występują duplikaty rekordów?

Można sprawdzić, czy występują duplikaty rekordów, bezpośrednio na stronie listy **Globalna książka adresowa**. W okienku akcji na karcie **Strona** w grupie **Obsługa** kliknij **Sprawdź duplikaty**. Następnie wybierz wartości do uwzględnienia podczas sprawdzania duplikatów.

## <a name="can-i-bulk-add-or-delete-party-records-from-an-address-book"></a>Czy można zbiorczo dodać lub usunąć rekordy stron z książki adresowej?

Tak, można dodać wiele rekordów stron do książki adresowej i również usunąć wielu rekordów stron.

- Aby dodać wiele rekordów stron do książki adresowej, na wybierz strony na stronie listy **Globalna książka adresowa**. Następnie w okienku akcji na karcie **Strona** w grupie **Obsługa** kliknij **Przypisz strony**. Wybierz książki adresowe, do których mają zostać dodane wybrane rekordy jednostek, a następnie kliknij przycisk **OK**. Wszystkie rekordy wybranych jednostek są dodawane do wybranych książek adresowych.
- Aby usunąć wiele rekordów stron z książki adresowej, na wybierz strony na stronie listy **Globalna książka adresowa**. Następnie w okienku akcji na karcie **Strona** w grupie **Obsługa** kliknij **Usuń strony**. Wybierz książki adresowe, z których chcesz usunąć jednostki, a następnie kliknij przycisk **OK**. Wszystkie rekordy wybranych jednostek są usuwane z wybranych książek adresowych.

## <a name="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one"></a>Czy można zmienić typ rekordu strony czy też należy usunąć stary rekord i utworzyć nowy?

Czasami trzeba zmienić typ rekordu strony z osoby na organizację lub z organizację na osobę. Na przykład Nancy jest członkiem zespołu sprzedaży w firmie Fabrikam Wielka Brytania. Na targach w Londynie spotyka sześciu nowych potencjalnych klientów. Dla każdego z nich Nancy tworzy rekord strony potencjalnego klienta. Gdy Nancy zapisuje rekordy, każdy rekord jest również tworzony w globalnej książce adresowej. Domyślnym typem strony w firmie Fabrikam jest organizacja, ale dla dwóch potencjalnych klientów trzeba ustawić typ rekordu jako osobę. W związku z tym gdy Nancy wraca z targów, musi ona zmienić typ stron dla dwóch rekordów potencjalnych klientów. Aby zmienić typ rekordu strony, należy najpierw utworzyć nowy rekord strony odpowiedniego typu w globalnej książce adresowej. Następnie należy skojarzyć stary rekord strony z nowym. Po skojarzeniu nowej strony należy usunąć oryginalny rekord strony z niewłaściwym typem.

## <a name="how-do-i-change-the-name-or-address-of-a-party-record"></a>Jak zmienić nazwę adres rekordu strony?

W każdej chwili można zaktualizować nazwę rekordu strony i adresy skojarzone z tym rekordem.

- Aby zaktualizować nazwę rekordu strony, otwórz rekordu strony, a następnie w okienku akcji kliknij przycisk **Edytuj**. Na skróconej karcie **Ogólne** wprowadź nową nazwę strony, a następnie zapisz rekord.
- Aby zaktualizować adres do rekordu strony, otwórz go, a następnie na skróconej karcie **Adresy** wybierz adres do zaktualizowania. Kliknij **Edytuj**, a następnie na stronie **Edytowanie adresów** dokonaj wymaganych zmian w adresie lub parametrach adresu.

## <a name="can-i-merge-two-or-more-party-records-into-one-record"></a>Czy można scalić dwa lub więcej rekordów stron w jeden rekord?

Czasami trzeba scalić dwa lub więcej rekordów stron w jednym rekordzie. Taka sytuacja może się zdarzyć po utworzeniu jednego lub kilku zduplikowanych rekordów stron, celowo lub przypadkowo. Podczas scalania rekordów stron wybiera się jeden, który zostanie zachowany. Informacje w innych rekordach są następnie scalane w tym jednym rekordzie. Na przykład okazuje się, że informacje o firmie Fabrikam są przechowywane w trzech rekordach stron: A, B i C. Postanawiasz zachować rekord A. Informacje przechowywane w rekordach stron B i C zostaną scalone w rekordzie jednostki A. W niektórych sytuacjach nie można scalać rekordów:

- Nie można scalać stron, które są skojarzone z tą samą rolę strony, np. odbiorcą lub dostawcą w tej samej firmie. Na przykład strona A jest skojarzona z odbiorcą w firmie 123, a strona B jest skojarzona z innym odbiorcą w firmie 123. Nie można scalić tych rekordów stron, bo gdyby zostały one scalone, powstały w ten sposób rekord byłby skojarzony z wieloma odbiorcami w jednej firmie, a to jest niedozwolone. Rekordy mogą zostać scalone, jeśli strona B jest skojarzona z dostawcą w firmie 123 lub odbiorcą w innej firmie.
- Nie można scalić wewnętrznych rekordów stron organizacji w jednej firmie, zespole lub jednostce operacyjnej.

## <a name="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page"></a>Czy należy utworzyć rekord strony w globalnej książce adresowej lub w innym miejscu, takim jak strony Odbiorca lub Dostawca?

Rekordy stron można wprowadzić w globalnej książce adresowej albo na stronie odpowiednie jednostki. Po dodaniu rekordu w jednym z tych miejsc, jest on zawsze dodawany w drugim miejscu. Na przykład jeśli dodasz rekord strony dla odbiorcy w globalnej książce adresowej, rekord jest również dodawany na stronie **Odbiorca**. Podobnie jeśli dodasz rekord strony dla odbiorcy na stronie **Odbiorca**, jest on również dodawany w globalnej książce adresowej. Aby określić, gdzie należy wprowadzać nowe rekordy stron, należy kierować się następującymi wskazówkami:

- **Tworzenie rekordu strony, gdy typ jednostki jest nieznany** — jeśli musisz utworzyć rekord strony, nie znając jej typu (np. nie wiesz, czy chodzi o klienta czy szansę biznesową), utwórz rekord w globalnej książce adresowej. Typ jednostki można wybrać później.
- **Tworzenie rekordu strony, gdy typ jednostki jest znany** — Jeśli znasz typ jednostki strony, możesz utworzyć rekord na odpowiedniej stronie dla tego typu. Na przykład, utwórz rekord odbiorcy na stronie **Odbiorca**. Po utworzeniu i zapisaniu rekordu przy użyciu odpowiedniej strony jednostki, rekord jest automatycznie tworzony w globalnej książce adresowej.

## <a name="can-i-translate-address-information-for-party-records"></a>Czy można tłumaczyć informacje adresowe dla rekordów stron?

Można ustawić tłumaczenia informacji adresowych, tak aby były wyświetlane w języku użytkownika (systemu) w programie, ale w innym języku w dokumentach, takich jak zamówienia sprzedaży. Można wprowadzić tłumaczenia nazw krajów/regionów, celów adresów oraz sekwencji nazw. Jeśli na przykład Twoim językiem jest duński, i chcesz utworzyć zamówienie sprzedaży dla klienta we Francji. W takim przypadku możesz wyświetlić rekord klienta po duńsku w programie, ale wyświetlić informacje adresowe po francusku w drukowanym zamówieniu sprzedaży. Podczas konfigurowania tłumaczenia należy wprowadzić tłumaczenie dla każdego elementu na liście. Elementy bez tłumaczenia będą zawsze wyświetlane w języku systemu. Jeśli na przykład Twoim językiem jest duński, i chcesz utworzyć zamówienie sprzedaży dla klienta we Francji. Jeśli nie wprowadzisz hiszpańskich (ESP) tłumaczeń informacji adresowych, będą one wyświetlane po duńsku zarówno w programie jaki w drukowanych dokumentach.
