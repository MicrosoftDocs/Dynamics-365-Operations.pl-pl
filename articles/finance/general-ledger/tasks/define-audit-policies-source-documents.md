---
title: Definiowanie zasad audytu dla dokumentów źródłowych
description: W tym temacie pokazano sposób konfigurowania i uruchamiania reguł inspekcji.
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba720fd1bbbbf8b4f3b936d65d9d7840432f291a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446880"
---
# <a name="define-audit-policies-for-source-documents"></a>Definiowanie zasad audytu dla dokumentów źródłowych

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób konfigurowania i uruchamiania reguł inspekcji. W przykładzie użyto raportów z wydatków hotelowych. Ta procedura wykorzystuje firmę demonstracyjną USMF. Rola audytora zawiera odpowiednie uprawnienia niezbędne do wykonania tych zadań.

1. W okienku nawigacji przejdź do **Moduły > Pulpit inspekcji > Ustawienia > Typ reguły**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa reguły** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. W polu **Nazwa kwerendy** wybierz opcję **Wiersz raportu wydatków**
6. W polu **typ kwerendy** wybierz opcję **Agregacja**.
7. W polu **Firma** wybierz **firmę**.
8. W polu **Odwołanie do daty dokumentu** wybierz opcję **Data i godzina modyfikacji**
9. Wybierz opcję **Zapisz**.
10. W okienku nawigacji przejdź do **Moduły > Pulpit inspekcji > Ustawienia > Zasady inspekcji**.
11. Wybierz pozycję **Nowy**.
12. W polu **Nazwa** wpisz wartość.
13. Rozwiń sekcję **Organizacje zasad**.
14. W drzewie zaznacz pozycję **Contoso Entertainment System USA**, a następnie wybierz **Dodaj**.
15. W drzewie zaznacz pozycję **Contoso Consulting USA**, a następnie wybierz **Dodaj**.
16. W drzewie zaznacz pozycję **Contoso Retail USA**, a następnie wybierz **Dodaj**.
17. Zwiń sekcję **Organizacje zasad**.
18. Rozwiń sekcję **Reguły zasad**.
19. Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.
20. Wybierz pozycję **Utwórz regułę**.
21. W polu **Data obowiązywania** wprowadź datę i godzinę.
22. Wybierz **Filtry**.
23. Na liście zaznacz wiersz **kategorii wydatku** oraz ustaw szczegóły dotyczące **hotelu**.
24. W polu **Kryteria** wprowadź lub wybierz wartość.
25. Wybierz kartę **Agreguj**.
26. Wybierz opcję **Dodaj**.
27. Na liście zaznacz wartość **Kwota transakcji**.
28. W polu **Pole** wprowadź lub wybierz wartość.
29. W polu **Funkcja agregująca** wybierz opcję **Suma**.
30. Wybierz kartę **Grupuj wg**.
31. Wybierz opcję **Dodaj**.
32. Na liście zaznacz wartość **Pracownik**.
33. Wybierz opcję **Dodaj**.
34. Na liście zaznacz wartość **Kategoria wydatku**.
35. W polu **Pole** wprowadź lub wybierz wartość.
36. Kliknij kartę **Posiadanie**.
37. Wybierz opcję **Dodaj**.
38. Zaznacz opcję **Kwota transakcji**.
39. W polu **Pole** wprowadź lub wybierz wartość.
40. W polu **Funkcja agregująca** wybierz opcję **Suma**.
41. W polu **Kryteria** wpisz wartość `>2000`.
42. Kliknij przycisk **OK**.
43. Wybierz **test**.
44. W polu **Data początkowa wyboru dokumentów** wprowadź datę i godzinę.
45. W polu **Data końcowa wyboru dokumentów** wprowadź datę i godzinę.
46. Wybierz **Uruchamianie przypadków testowych**.
47. W okienku akcji kliknij pozycję **Zasady inspekcji**.
48. Wybierz **Opcje dodatkowe**.
49. W polu **Data rozpoczęcia** wprowadź datę i godzinę.
50. W polu **Data zakończenia** wprowadź datę i godzinę.
51. Wybierz **Partia**.
52. Rozwiń sekcję **Uruchom w tle**.
53. W polu **Przetwarzanie wsadowe** zaznacz opcję **Tak**.
54. Kliknij przycisk **OK**.
55. W okienku nawigacji przejdź do **Moduły > Pulpit inspekcji > Sprawy inspekcji**.
56. Na liście znajdź i zaznacz odpowiedni rekord.
57. Rozwiń sekcję **Powiązania**.
58. Na liście znajdź i zaznacz odpowiedni rekord.

