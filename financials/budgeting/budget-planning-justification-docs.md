---
title: "Dokumenty uzasadnienia planowania budżetu"
description: "Dokumenty uzasadnienia dostarczają osobom wnioskującym o budżet wyjaśnień, dlaczego utworzenie określonego budżetu jest niezbędne."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 1d23c0e1725a39d25d2be8971f541b2c31bbe859
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Dokumenty uzasadnienia planowania budżetu
<a id="budget-planning-justification-documents" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Dokumenty uzasadnienia dostarczają osobom wnioskującym o budżet wyjaśnień, dlaczego utworzenie określonego budżetu jest niezbędne. 

Menedżera budżetu tworzy szablon planu budżetu w programie Microsoft Word i przypisuje go do bieżącego procesu planowania budżetu. Następnie właściciele budżetów mogą otworzyć szablon i automatycznie wypełnić dane w programie Word na podstawie swoich żądań budżetów. Potem mogą wprowadzić dodatkowy tekst lub dane, a następnie zapisać i dołączyć spersonalizowany dokument uzasadnienia do planu budżetu.

##### Konfigurowanie dodatku pakietu Office dla usługi Microsoft Dynamics dla programu Word
<a id="set-up-microsoft-dynamics-office-add-in-for-microsoft-word" class="xliff"></a>

1.  Otwórz nowy dokument programu Microsoft Word.
2.  Na wstążce kliknij przycisk **Wstaw**, a następnie kliknij opcję **Sklep**.
3.  Wyszukaj dodatek pakietu Office dla usługi Microsoft Dynamics i kliknij przycisk **Dodaj**.
4.  W programie Word w prawym okienku kliknij opcję **Dodaj informacje dotyczące serwera**.
5.  Wpisz lub wklej adres URL serwera i kliknij przycisk **OK**.

##### Definiowanie szablonu uzasadnienia w programie Microsoft Word
<a id="define-the-justification-template-in-microsoft-word" class="xliff"></a>

1.  Po zalogowaniu w dodatku pakietu Office dla usługi Microsoft Dynamics kliknij opcję **Projekt**.
2.  Dla informacji nagłówka użyj przycisku **Dodaj pola**.
3.  Zaznacz źródło danych jednostki BudgetPlanJustification, a następnie kliknij przycisk **Dalej**. **Uwaga:** Ta jednostka jest wymagana dla każdego dokumentu uzasadnienia. Mogą być używane również inne jednostki , ale w razie braku tej jednostki przekazywanie z powrotem do usługi Microsoft Dynamics 365 for Finance and Operations Enterprise Edition zakończy się niepowodzeniem.
4.  W dokumencie programu Word dodaj etykiety i wartości BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter i DocumentNumber. **Uwaga:** W razie potrzeby można użyć własnych spersonalizowanych etykiet zamiast standardowych etykiet.
5.  Kliknij przycisk **Gotowe**, aby zakończyć konfigurowanie sekcji nagłówka.
6.  Dla szczegółów kwot planu budżetu na poziomie wiersza kliknij opcję **Dodaj tabelę**.
7.  Ponownie zaznacz źródło danych jednostki BudgetPlanJustification, a następnie kliknij przycisk **Dalej**.
8.  Dodaj pola EffectiveDate, ScenarioName, AccountDisplayValue i AccountingCurrencyExpenseAmount. **Uwaga:** Jeśli są dostępne komentarze do dodania w indywidualnych wierszach planu budżetu, można je dodać do tabeli w tym miejscu.
9.  Wprowadź wszelkie dodatkowe instrukcje dla użytkownika końcowego i zastosuj do dokumentu niezbędne formatowanie lub style.
10. Zapisz dokument na lokalnym komputerze i zamknij plik.

##### Konfigurowanie używania szablonu uzasadnienia w procesie planowania budżetu
<a id="set-up-the-budget-planning-process-to-use-the-justification-template" class="xliff"></a>

1.  W programie Finance and Operations wybierz kolejno opcje **Budżetowanie** &gt; **Ustawienia** &gt; **Planowanie budżetu** &gt; **Szablony dokumentów uzasadnienia**.
2.  Kliknij przycisk **Nowy** i przejdź do nowo utworzonego dokumentu programu Microsoft Word.
3.  Nadaj szablonowi nazwę wyświetlaną i opis. Kliknij przycisk **OK**
4.  Wybierz kolejno opcje **Budżetowanie** &gt; **Ustawienia** &gt; **Planowanie** **budżetu** &gt; **Proces planowania budżetu**.
5.  Zaznacz proces, w którym ma być używany szablon uzasadnienia, i kliknij przycisk **Edytuj**.
6.  W polu **Szablon dokumentu uzasadnienia** zaznacz odpowiedni szablon i zapisz.

##### Edytowanie i zapisywanie spersonalizowanych dokumentów uzasadnienia
<a id="edit-and-save-personalized-justification-documents" class="xliff"></a>

1.  W programie Finance and Operations utwórz nowy planu budżetu lub otwórz istniejący plan budżetu.
2.  W menu rozwijanym **Uzasadnienie** wybierz polecenie **Utwórz nowe uzasadnienie**.
3.  Wypełnij pola szczegółów, a następnie w menu rozwijanym **Uzasadnienie** wybierz opcję przekazania spersonalizowanego dokumentu.





