---
title: Dokumenty uzasadnienia planowania budżetu
description: Dokumenty uzasadnienia dostarczają osobom wnioskującym o budżet wyjaśnień, dlaczego utworzenie określonego budżetu jest niezbędne.
author: panolte
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9ca0c291b5d446325f6be6b6bed612bd26e7c640
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019210"
---
# <a name="budget-planning-justification-documents"></a>Dokumenty uzasadnienia planowania budżetu

[!include [banner](../includes/banner.md)]

Dokumenty uzasadnienia dostarczają osobom wnioskującym o budżet wyjaśnień, dlaczego utworzenie określonego budżetu jest niezbędne. 

Menedżera budżetu tworzy szablon planu budżetu w programie Microsoft Word i przypisuje go do bieżącego procesu planowania budżetu. Następnie właściciele budżetów mogą otworzyć szablon i automatycznie wypełnić dane w programie Word na podstawie swoich żądań budżetów. Potem mogą wprowadzić dodatkowy tekst lub dane, a następnie zapisać i dołączyć spersonalizowany dokument uzasadnienia do planu budżetu.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Konfigurowanie dodatku Microsoft Dynamics do obsługi programu Microsoft Word

1.  Otwórz dokument programu Microsoft Word.
2.  Na wstążce kliknij przycisk **Wstaw**, a następnie kliknij opcję **Sklep**.
3.  Wyszukaj dodatek pakietu Office dla usługi Microsoft Dynamics i kliknij przycisk **Dodaj**.
4.  W programie Word w prawym okienku kliknij opcję **Dodaj informacje dotyczące serwera**.
5.  Wpisz lub wklej adres URL serwera i kliknij przycisk **OK**.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Definiowanie szablonu uzasadnienia w programie Microsoft Word

1.  Po zalogowaniu w dodatku pakietu Office dla usługi Microsoft Dynamics kliknij opcję **Projekt**.
2.  Dla informacji nagłówka użyj przycisku **Dodaj pola**.
3.  Zaznacz źródło danych jednostki BudgetPlanJustification, a następnie kliknij przycisk **Dalej**. **Uwaga:** Ta jednostka jest wymagana dla każdego dokumentu uzasadnienia. Mogą być używane również inne jednostki, ale w razie braku tej jednostki przekazywanie z powrotem do Microsoft Dynamics 365 Finance zakończy się niepowodzeniem.
4.  W dokumencie programu Word dodaj etykiety i wartości BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter i DocumentNumber. **Uwaga:** W razie potrzeby można użyć własnych spersonalizowanych etykiet zamiast standardowych etykiet.
5.  Kliknij przycisk **Gotowe**, aby zakończyć konfigurowanie sekcji nagłówka.
6.  Dla szczegółów kwot planu budżetu na poziomie wiersza kliknij opcję **Dodaj tabelę**.
7.  Ponownie zaznacz źródło danych jednostki BudgetPlanJustification, a następnie kliknij przycisk **Dalej**.
8.  Dodaj pola EffectiveDate, ScenarioName, AccountDisplayValue i AccountingCurrencyExpenseAmount. **Uwaga:** Jeśli są dostępne komentarze do dodania w indywidualnych wierszach planu budżetu, można je dodać do tabeli w tym miejscu.
9.  Wprowadź wszelkie dodatkowe instrukcje dla użytkownika końcowego i zastosuj do dokumentu niezbędne formatowanie lub style.
10. Zapisz dokument na lokalnym komputerze i zamknij plik.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Konfigurowanie używania szablonu uzasadnienia w procesie planowania budżetu

1.  Wybierz kolejno opcje **Budżetowanie** &gt; **Ustawienia** &gt; **Planowanie budżetu** &gt; **Szablony dokumentów uzasadnienia**.
2.  Kliknij przycisk **Nowy** i przejdź do nowo utworzonego dokumentu programu Microsoft Word.
3.  Nadaj szablonowi nazwę wyświetlaną i opis. Kliknij przycisk **OK**
4.  Wybierz kolejno opcje **Budżetowanie** &gt; **Ustawienia** &gt; **Planowanie** **budżetu** &gt; **Proces planowania budżetu**.
5.  Zaznacz proces, w którym ma być używany szablon uzasadnienia, i kliknij przycisk **Edytuj**.
6.  W polu **Szablon dokumentu uzasadnienia** zaznacz odpowiedni szablon i zapisz.

##### <a name="edit-and-save-personalized-justification-documents"></a>Edytowanie i zapisywanie spersonalizowanych dokumentów uzasadnienia

1.  Utwórz plan budżetu lub otwórz istniejący plan budżetu.
2.  W menu rozwijanym **Uzasadnienie** wybierz polecenie **Utwórz nowe uzasadnienie**.
3.  Wypełnij pola szczegółów, a następnie w menu rozwijanym **Uzasadnienie** wybierz opcję przekazania spersonalizowanego dokumentu.




