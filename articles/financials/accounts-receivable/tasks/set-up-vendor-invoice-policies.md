---
title: Konfigurowanie zasad faktur od dostawców
description: W tym temacie wyjaśniono, jak skonfigurować zasady faktury od dostawcy w Dynamics 365 for Finance and Operatoins.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 328aafd16496fdbb963c9aa40a5c13005be7a382
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842816"
---
# <a name="set-up-vendor-invoice-policies"></a>Konfigurowanie zasad faktur od dostawców

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym temacie wyjaśniono, jak skonfigurować zasady faktury od dostawcy w Dynamics 365 for Finance and Operatoins. Zasady dotyczące faktur od dostawców są uruchamiane podczas księgowania faktur od dostawców przy użyciu strony Faktura od dostawcy oraz po otwarciu strony naruszeń zasad faktur od dostawców. Można także skonfigurować przepływ pracy faktur od dostawcy, aby uruchamiał zasady dotyczące faktur od dostawców podczas każdego przesłania faktur do przepływu. 

- Zasady faktur od dostawców nie dotyczą faktur, które zostały utworzone w rejestrze faktur lub arkuszu faktur.  
- Funkcja sprawdzania poprawności uzgadniania faktur nie używa zasad dotyczących faktur od dostawców, ale jest konfigurowana na stronie Parametry modułu rozrachunków z dostawcami.  
- To nagranie wykorzystuje firmę demonstracyjną USMF. Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości. Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Przygotowanie do tworzenia zasad dotyczących faktur od dostawców
1. Otwórz **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami**.
2. Kliknij kartę **Weryfikacja faktury**
3. Zaznacz lub wyczyść pole wyboru **Automatycznie aktualizuj stan nagłówka faktury**.
4. Kliknij przycisk **OK**.
5. W polu **Księguj fakturę z rozbieżnościami** zaznacz opcję.
6. Zamknij stronę.
7. Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców**.
8. Wybierz **Parametry**.
9. Wybierz opcję **Dodaj**.
10. Zamknij tę stronę, aby powrócić do strony głównej.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Tworzenie typów reguł dla faktur od dostawców
1. Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Typy reguł faktur od dostawców**.
2. Wybierz pozycję **Nowy**.
3. W polach **Nazwa reguły** i **Opis** wpisz wartości.
4. W polu **Nazwa kwerendy** wybierz przycisk listy rozwijanej, aby otworzyć wyszukiwanie, a następnie kliknij odpowiedni rekord.
5. Wybierz opcję **Zapisz**.
6. Zamknij tę stronę, aby powrócić do strony głównej.

## <a name="define-a-vendor-invoice-policy"></a>Definiowanie zasad dotyczących faktur od dostawców
1. Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców**.
2. Wybierz pozycję **Nowy**.
3. W polach **Nazwa** i **Opis** wpisz wartości.
4. Rozwiń lub zwiń sekcję **Organizacje zasad**.
5. W drzewie zaznacz pozycję **Contoso Entertainment System USA**.
6. Wybierz opcję **Dodaj**.
7. Rozwiń lub zwiń sekcję **Reguły zasad**.
8. Wybierz pozycję **Utwórz regułę**.
9. W polu **Opis reguły** wpisz wartość.
10. Wybierz **Filtry**.
11. Wybierz opcję **Dodaj**. Wybierz odpowiedni rekord.
12. W polach **Tabela**, **Tabela pochodna** i **Pole**, wybierz lub wprowadź opcje z menu rozwijanego.
13. Zamknij stronę.
14. W polu **Kryteria** wpisz wartość.
15. Kliknij przycisk **OK**.
16. Kliknij przycisk **OK**.
17. Zamknij te strony, aby powrócić do strony głównej.

