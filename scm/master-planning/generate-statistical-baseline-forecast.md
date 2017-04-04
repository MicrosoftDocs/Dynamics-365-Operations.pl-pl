---
title: Generowanie planu bazowego statystycznej prognozy
description: "Ten artykuł zawiera informacje dotyczące parametrów i filtrów, które są używane w obliczeniach prognozy popytu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c0c918b94fe96d123bb6c25c42fe168a026cd8a9
ms.lasthandoff: 03/31/2017


---

# <a name="generate-a-statistical-baseline-forecast"></a>Generowanie planu bazowego statystycznej prognozy

Ten artykuł zawiera informacje dotyczące parametrów i filtrów, które są używane w obliczeniach prognozy popytu. 

Po utworzeniu prognozy podstawowej, należy określić najpierw parametry i filtry, które są używane w obliczeniach. Na przykład można utworzyć podstawową prognozę, która szacuje popyt na podstawie danych transakcji z minionego roku dla określonej firmy, na najbliższy miesiąc i dla wybranej grupy towarów. 

Aby wygenerować prognozy popytu, przejdź do **Master planning &gt;Prognozowanie &gt;Prognozowanie popytu &gt;Generuj bazowa Prognoza statystyczna**. 

Przedział prognozy można wybrać w czasie generowania prognozy. Dostępne są następujące wartości: Dzień, Tydzień i Miesiąc. 

Liczbę przedziałów, dla których generuje się prognozę, ustawia się w polu **Horyzont prognozy**. 

Gdy strategia prognoza jest ustawiona na **Kopiuj na popycie historycznym**, koniec horyzontu historycznego jest ignorowany. System kopiuje numer pakiety, określona w **Horyzont prognozy** pola do prognozy popytu, począwszy od daty, w **od daty** pole w obszarze **historyczne horyzont**. Kopiując popyt historyczny z określonej daty rozpoczęcia w przód, pracownicy odpowiedzialni za planowanie produkcji mogą zaplanować następny kwartał na dwa sposoby:

-   Kopiując popyt z tego samego kwartału roku ubiegłego.
-   Kopiując popyt z poprzedniego kwartału.

Aby uniknąć nieporozumień w planach produkcji, pewną liczbę przedziałów prognozy można zablokować. Tę liczbę ustala się w polu **Horyzont czasowy zamrożenia**. Na stronie **Skorygowana prognoza popytu** komórki dla zamrożonych przedziałów są wyłączone, by pokazać, że tych wartości nie należy zmieniać. 

Data rozpoczęcia dla bazowa prognozy popytu nie musi być datą bieżącą ani datę w przyszłości. Aby ustawić inną datę rozpoczęcia, użyj pola **Data początkowa prognozy bazowej — Od daty**. Na przykład w czerwcu, użytkownicy mogą wygenerować prognozę w następnym roku. Ponieważ brakuje przedziałów prognozy między końcem prognozy historycznej a początkiem prognozy bazowej, przewidywania mogą być nieprecyzyjne. Jeśli używasz Microsoft Dynamics 365 dla operacji żądanie prognozowania usługi istnieją cztery sposoby, w których można wypełnić brakujące luki. Można wybrać metodę, która ma przez ustawienie Brak\_wartość\_PODSTAWIENIE parametru na **prognozowania parametrów popytu** strony. 

**Data rozpoczęcia prognozy według planu bazowego** - **od daty** pole musi być ustawiony na początku Wiadro prognozy, na przykład, w Stanach Zjednoczonych w niedzielę, jeśli prognozowania Wiadro jest tydzień. System automatycznie ustawi **Data rozpoczęcia prognozy według planu bazowego** - **od daty** pole, aby odpowiadać na początku prognozy Wiadro z farbą. 

**Data rozpoczęcia prognozy według planu bazowego** - **od daty** pole można ustawić na datę w w przeszłości. Innymi słowy można wygenerować prognozę popytu w przeszłości. Jest to przydatne, ponieważ pozwala regulować parametry usługi prognozy, aby statystyczna prognoza generowana w przeszłości pasowała do historycznego popytu. Użytkownicy mogą dalej używać tych ustawień parametrów do generowania bazowej prognozy statystycznej dla przyszłości. 

Ręczne korekty wprowadzane w poprzednich iteracjach prognozowania popytu mogą być automatycznie stosowane do nowej podstawowej prognozy, ale musi być zaznaczone pole wyboru **Przenieś ręczne korekty prognozy popytu**. Jeśli pole wyboru nie jest zaznaczone, ręczne korekty nie są dodawane do prognozy bazowej, ale nie są też usuwane. Ręczne korekty prognozy można usunąć tylko w momencie importu prognozy, usuwając zaznaczenie pola wyboru **Zapisz korekty ręczne bazowej prognozy popytu**. Ręczne korekty są zapisywane w chwili autoryzacji. W związku z tym jeśli użytkownik sprawia, że ręcznego dopasowania do prognozy, ale nie dopuszczają prognozy do 365 Dynamics dla operacji, zmiany zostaną utracone. Aby uzyskać więcej informacji na temat ręcznego dopasowania i sposobu ich działania, zobacz [autoryzowanie skorygowana Prognoza](authorize-adjusted-forecast.md). 

Generowanie prognozy popytu może obejmować nazwę i komentarze, by ułatwić użytkownikom identyfikowanie prognoz, które zostały wygenerowany. Te wartości są widoczne w historii generowania prognozy na stronie **Historia generowania bazowej prognozy statystycznej**. 

Podczas generowania prognozy można używać międzyfirmowej grupy planowania, kluczy alokacji produktów i innych filtrów. Mogą one służyć do poprawiania skuteczności lub dzielenia danych na łatwe w zarządzaniu fragmenty. Warto jednak zwrócić uwagę, że prognoza popytu nie jest generowana dla członków żadnego z kluczy alokacji produktów skojarzonych z międzyfirmową grupą planowania, nawet jeśli w zapytaniu zostanie wybrany klucz alokacji produktów. 

**Porada**: czasami podczas generowania prognozy popytu lub gdy prognoza zostanie wygenerowana bez dziennika sesji, użytkownikom mogą być wyświetlane błędy. Przyczyną mogą dane zostawione w zapytaniu, które zostały wcześniej użyte do wygenerowania prognozy. Aby temu zaradzić, należy kliknąć **Wybierz**, aby otworzyć stronę **Zapytanie**, kliknąć **Resetuj**, a następnie ponownie wygenerować prognozę bazową. 

Jeżeli prognozy nie jest generowany dla duży zestaw elementów, ale na przykład dla jednego towaru lub klucz alokacji towaru jeden w naraz, a następnie w celu uzyskania lepszej wydajności, można wybrać **Użyj żądania odpowiedzi trybu** pole wyboru na **wzorca, prognozowanie planowania popytu - Setup -** - **prognozowania parametrów - analityków popytu** kartę.

<a name="see-also"></a>Informacje dodatkowe
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)


