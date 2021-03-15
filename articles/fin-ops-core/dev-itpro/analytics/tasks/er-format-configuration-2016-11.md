---
title: ER Tworzenie konfiguracji formatu (listopad 2016)
description: W tym temacie wyjaśniono sposób tworzenia konfiguracji formatu raportowania elektronicznego (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9404d1e242c83d2103d1f24c42589c33b9f57f02
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092257"
---
# <a name="er-create-a-format-configuration-november-2016"></a>ER Tworzenie konfiguracji formatu (listopad 2016)

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć konfigurację formatu dla raportowania elektronicznego (ER). Ta konfiguracja formatu określi format dokumentów elektronicznych, które będą używane do przetwarzania płatności. W tym przykładzie utworzysz konfigurację formatu dla przykładowej firmy Litware, Inc. W celu wykonania tych kroków należy najpierw wykonać procedurę „Mapowanie modelu na wybrane źródła danych”.


## <a name="create-a-new-format-configuration"></a>Utwórz nową konfigurację formatu.
1. Wybierz kolejno opcje **Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne**.
2. Kliknij opcję **Konfiguracje raportowania**.
3. W drzewie zaznacz element **Płatności (model uproszczony)**.
4. Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.

 > [!NOTE]
 > Jeśli nie widać przycisku **Utwórz konfigurację**, należy włączyć tryb projektowania na stronie **Parametry raportowania elektronicznego**. 
 
5. W polu **Nowy** wpisz **Format oparty na modelu danych PaymentModel**.
6. W polu **Nazwa** wpisz **BACS (fikcyjny brytyjski)**.
7. W polu **Opis** wpisz **Format płatności dla dostawcy BACS (fikcyjny brytyjski)**.
    * Aktywny dostawca konfiguracji jest automatycznie umieszczany w tym miejscu. Ten dostawca będzie mógł obsługiwać tę konfigurację. Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.  
    * Można zdefiniować określony format dokumentu elektronicznego. Pozostaw to pole puste, aby wybrać format w czasie wykonywania.  
8. W polu **Definicja modelu danych** wprowadź lub wybierz wartość.
9. Kliknij przycisk **Utwórz konfigurację**. Utworzono nową konfigurację. Wersja robocza może służyć do przechowywania formatu projektu w celu zarządzania dokumentami elektronicznymi.  

## <a name="design-the-format-of-an-electronic-document"></a>Zaprojektuj format dokumentu elektronicznego.
1. Kliknij przycisk **Konstruktor**.
2. Kliknij przycisk **Dodaj element główny**, aby otworzyć rozwijane okno dialogowe.
3. W drzewie zaznacz element **Wspólne\Plik**.
4. W polu **Nazwa** wpisz **Xml**.
5. W polu **Kodowanie** wpisz **UTF-8**.
6. Kliknij przycisk **OK**.
7. Kliknij przycisk **Dodaj**.
8. W drzewie zaznacz element **XML\Element**.
9. W polu **Nazwa** wpisz **Komunikat**.
10. Kliknij przycisk **OK**.
11. W drzewie zaznacz element **Xml\Komunikat**.
12. Kliknij opcję **Dodaj element**.
13. W polu **Nazwa** wpisz **ProcessingDate**.
14. Kliknij przycisk **OK**.
15. Kliknij opcję **Dodaj element**.
16. W polu Nazwa wpisz **MessageId**.
17. Kliknij przycisk **OK**.
18. Kliknij opcję **Dodaj element**.
19. W polu **Nazwa** wpisz **Płatności**.
20. Kliknij przycisk **OK**.
21. W drzewie zaznacz element **Xml\Komunikat\Płatności**.
22. Kliknij opcję **Dodaj element**.
23. W polu **Nazwa** wpisz **Towar**.
24. Kliknij przycisk **OK**.
25. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.
26. Kliknij przycisk **Dodaj**.
27. W drzewie zaznacz element **XML\Atrybut**.
28. W polu Nazwa wpisz **Identyfikator**
29. Kliknij przycisk **OK**.
30. Kliknij przycisk **Dodaj**.
31. W drzewie zaznacz element **XML\Element**.
32. W polu Nazwa wpisz **Dostawca**.
33. Kliknij przycisk **OK**.
34. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca**.
35. Kliknij opcję **Dodaj element**.
36. W polu Nazwa wpisz **Nazwa**.
37. Kliknij przycisk **OK**.
38. Kliknij opcję **Dodaj element**.
39. W polu **Nazwa** wpisz **Bank**.
40. Kliknij przycisk **OK**.
41. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank**.
42. Kliknij opcję **Dodaj element**.
43. W polu **Nazwa** wpisz **RoutingNumber**.
44. Kliknij przycisk **OK**.
45. Kliknij opcję **Dodaj element**.
46. W polu **Nazwa** wpisz **AccountNumber**.
47. Kliknij przycisk **OK**.
48. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca**.
49. Kliknij opcję **Kopiuj**.
50. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.
51. Kliknij opcję **Wklej**.
52. W polu **Nazwa** wpisz **Płatnik**.
53. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar**.
54. Kliknij opcję **Dodaj element**.
55. W polu **Nazwa** wpisz **Waluta**.
56. Kliknij przycisk **OK**.
57. Kliknij opcję **Dodaj element**.
58. W polu **Nazwa** wpisz **Opis**.
59. Kliknij przycisk **OK**.
60. Kliknij opcję **Dodaj element**.
61. W polu Nazwa wpisz **TransDate**.
62. Kliknij przycisk **OK**.
63. Kliknij opcję **Dodaj element**.
64. W polu Nazwa wpisz **Kwota**.
65. Kliknij przycisk **OK**.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Przygotuj składniki formatu w celu zmapowania na elementy modelu danych.
1. W drzewie zaznacz element **Xml\Komunikat\ProcessingDate**.
2. Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.
3. W drzewie zaznacz element **Tekst\DateTime**.
4. W polu **Format** wpisz **rrrr-MM-dd**.
5. Kliknij przycisk **OK**.
6. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\TransDate**.
7. Kliknij opcję **Dodaj datę/godzinę**.
8. W polu **Format** wpisz **rrrr-MM-dd**.
9. W polu **Typ daty/godziny** wybierz opcję **Data**.
10. Kliknij przycisk **OK**.
11. W drzewie zaznacz element **Xml\Komunikat\MessageId**.
12. Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.
13. W drzewie zaznacz element **Tekst\Ciąg**.
14. Kliknij przycisk **OK**.
15. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa**.
16. Kliknij opcję **Dodaj ciąg**.
17. Kliknij przycisk **OK**.
18. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank\RoutingNumber**.
19. Kliknij opcję **Dodaj ciąg**.
20. Kliknij przycisk **OK**.
21. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Dostawca\Bank\AccountNumber**.
22. Kliknij opcję **Dodaj ciąg**.
23. Kliknij przycisk **OK**.
24. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Nazwa**.
25. Kliknij opcję **Dodaj ciąg**.
26. Kliknij przycisk **OK**.
27. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Bank\RoutingNumber**.
28. Kliknij opcję **Dodaj ciąg**.
29. Kliknij przycisk **OK**.
30. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Płatnik\Bank\AccountNumber**.
31. Kliknij opcję **Dodaj ciąg**.
32. Kliknij przycisk **OK**.
33. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Waluta**.
34. Kliknij opcję **Dodaj ciąg**.
35. Kliknij przycisk **OK**.
36. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Opis**.
37. Kliknij opcję **Dodaj ciąg**.
38. Kliknij przycisk **OK**.
39. W drzewie zaznacz element **Xml\Komunikat\Płatności\Towar\Kwota**.
40. Kliknij opcję **Dodaj ciąg**.
41. Kliknij przycisk **OK**.
42. Kliknij przycisk **Zapisz**.
43. Zamknij stronę.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]