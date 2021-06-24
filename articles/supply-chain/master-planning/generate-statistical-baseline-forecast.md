---
title: Generowanie bazowej prognozy statystycznej
description: Ten temat zawiera informacje dotyczące parametrów i filtrów, które są używane w obliczeniach prognozy popytu.
author: roxanadiaconu
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 780d1e1307b69ec9a31d032039970de454160d6f
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189699"
---
# <a name="generate-a-statistical-baseline-forecast"></a>Generowanie bazowej prognozy statystycznej

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące parametrów i filtrów, które są używane w obliczeniach prognozy popytu. 

Po utworzeniu prognozy podstawowej, należy określić najpierw parametry i filtry, które są używane w obliczeniach. Na przykład można utworzyć podstawową prognozę, która szacuje popyt na podstawie danych transakcji z minionego roku dla określonej firmy, na najbliższy miesiąc i dla wybranej grupy towarów. 

Aby wygenerować prognozę popytu, wybierz kolejno opcje **Planowanie główne &gt; Prognozowanie &gt; Prognozowanie popytu &gt; Generuj bazową prognozę statystyczną**. 

Przedział prognozy można wybrać w czasie generowania prognozy. Dostępne są następujące wartości: Dzień, Tydzień i Miesiąc. 

Liczbę przedziałów, dla których generuje się prognozę, ustawia się w polu **Horyzont prognozy**. 

Gdy strategia prognoza jest ustawiona na **Kopiuj na popycie historycznym**, koniec horyzontu historycznego jest ignorowany. System kopiuje liczbę przedziałów określoną w polu **Horyzont prognozy** do prognozy popytu, począwszy od daty ustawionej w polu **Od dnia** w obszarze **Horyzont historyczny**. Kopiując popyt historyczny z określonej daty rozpoczęcia w przód, pracownicy odpowiedzialni za planowanie produkcji mogą zaplanować następny kwartał na dwa sposoby:

-   Kopiując popyt z tego samego kwartału roku ubiegłego.
-   Kopiując popyt z poprzedniego kwartału.

Aby uniknąć nieporozumień w planach produkcji, pewną liczbę przedziałów prognozy można zablokować. Tę liczbę ustala się w polu **Horyzont czasowy zamrożenia**. Na stronie **Skorygowana prognoza popytu** komórki dla zamrożonych przedziałów są wyłączone, by pokazać, że tych wartości nie należy zmieniać. 

Data rozpoczęcia dla bazowa prognozy popytu nie musi być datą bieżącą ani datę w przyszłości. Aby ustawić inną datę rozpoczęcia, użyj pola **Data początkowa prognozy bazowej — Od daty**. Na przykład w czerwcu, użytkownicy mogą wygenerować prognozę w następnym roku. Ponieważ brakuje przedziałów prognozy między końcem prognozy historycznej a początkiem prognozy bazowej, przewidywania mogą być nieprecyzyjne. Jeśli używasz usługi prognozowania popytu, masz do dyspozycji sposoby wypełniania brakujących miejsc. Metodę wybiera się, ustawiając parametr MISSING\_VALUE\_SUBSTITUTION na stronie **Parametry prognozowania popytu**. 

> [!NOTE]
> Brak podstawiania wartości dotyczy tylko przerw w danych między datą początkową i końcową dla danych historycznych. Nie będzie on wypełniać danych przed lub po ostatnim fizycznym punkcie danych, jest traktowany jak ekstrapolacja między rzeczywistymi istniejącymi punktami danych. 

Pole **Data początkowa prognozy bazowej** - **Od dnia** musi być ustawione na początek przedziału prognozy, np. w Stanach Zjednoczonych w niedzielę, jeśli przedziałem prognozowania jest tydzień. System automatycznie dopasowuje pole **Data początkowa prognozy bazowej** - **Od dnia** do początku przedziału prognozy. 

Pole **Data początkowa prognozy bazowej** - **Od dnia** może być ustawione na datę w przeszłości. Innymi słowy można wygenerować prognozę popytu w przeszłości. Jest to przydatne, ponieważ pozwala zmieniać parametry usługi prognozy, aby statystyczna prognoza generowana w przeszłości pasowała do historycznego popytu. Użytkownicy mogą dalej używać tych ustawień parametrów do generowania bazowej prognozy statystycznej dla przyszłości. 

Ręczne korekty wprowadzane w poprzednich iteracjach prognozowania popytu mogą być automatycznie stosowane do nowej podstawowej prognozy, ale musi być zaznaczone pole wyboru **Przenieś ręczne korekty prognozy popytu**. Jeśli pole wyboru nie jest zaznaczone, ręczne korekty nie są dodawane do prognozy bazowej, ale nie są też usuwane. Ręczne korekty prognozy można usunąć tylko w momencie importu prognozy, usuwając zaznaczenie pola wyboru **Zapisz korekty ręczne bazowej prognozy popytu**. Ręczne korekty są zapisywane w chwili autoryzacji. Z tego względu jeśli użytkownik dokonuje ręcznej korekty prognozy, ale nie autoryzuje prognozy wstecz w programie Supply Chain Management, zmiany są tracone. Aby uzyskać więcej informacji o ręcznych korektach i sposobie ich działania, zobacz [Autoryzowanie skorygowanej prognozy](authorize-adjusted-forecast.md). 

Generowanie prognozy popytu może obejmować nazwę i komentarze, by ułatwić użytkownikom identyfikowanie prognoz, które zostały wygenerowany. Te wartości są widoczne w historii generowania prognozy na stronie **Historia generowania bazowej prognozy statystycznej**. 

Podczas generowania prognozy można używać międzyfirmowej grupy planowania, kluczy alokacji produktów i innych filtrów. Mogą one służyć do poprawiania skuteczności lub dzielenia danych na łatwe w zarządzaniu fragmenty. Warto jednak zwrócić uwagę, że prognoza popytu nie jest generowana dla członków żadnego z kluczy alokacji produktów skojarzonych z międzyfirmową grupą planowania, nawet jeśli w zapytaniu zostanie wybrany klucz alokacji produktów. 

> [!TIP]
> Wskazówka: czasami podczas generowania prognozy popytu lub gdy prognoza zostanie wygenerowana bez dziennika sesji, użytkownikom mogą być wyświetlane błędy. Przyczyną mogą dane zostawione w zapytaniu, które zostały wcześniej użyte do wygenerowania prognozy. Aby temu zaradzić, należy kliknąć **Wybierz**, aby otworzyć stronę **Zapytanie**, wybrać **Resetuj**, a następnie ponownie wygenerować prognozę bazową. 

Jeśli prognoza nie jest generowana dla dużego zestawu towarów, ale na przykład dla jednego towaru lub jednego klucza alokacji produktów, wówczas aby poprawić wydajność procesu, można zaznaczyć pole wyboru **Użyj trybu odpowiedzi na żądanie** na karcie **Planowanie główne - Ustawienia - Prognozowanie popytu** - **Parametry prognozowania popytu - Uczenie maszynowe Azure**.

> [!NOTE]
> Prognoza o potencjalnie płaskim wyglądzie może być spowodowana przez historyczne dane, które mają być dłuższego okresu historycznego (co najmniej 3 okresy w celu wybrania wzorców, np. 3 lata z prognozą miesięczną). Aby uzyskać lepszy rezultat, można spróbować zmienić stopień szczegółowości zakresu czasu lub wydłużyć zakres czasu.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Ustawienia prognozowania popytu](demand-forecasting-setup.md)

- [Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)

- [Autoryzowanie skorygowanej prognozy](authorize-adjusted-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]