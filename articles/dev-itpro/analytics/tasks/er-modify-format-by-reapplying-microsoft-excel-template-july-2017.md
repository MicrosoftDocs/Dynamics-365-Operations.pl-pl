--- 
title: Modyfikowanie formatu przez ponowne zastosowanie szablonu programu Microsoft Excel na potrzeby raportowania elektronicznego (ER)
description: "W celu wykonania kroków w tej procedurze należy najpierw wykonać procedurę „ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML”."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: b49cfe39732a450e4723419c50d8bcc3d64b7ec9
ms.openlocfilehash: 2f35727376812b0de428ce929ebe0d33bc497984
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="modify-a-format-by-reapplying-a-microsoft-excel-template-for-electronic-reporting-er"></a>Modyfikowanie formatu przez ponowne zastosowanie szablonu programu Microsoft Excel na potrzeby raportowania elektronicznego (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W celu wykonania kroków w tej procedurze należy najpierw wykonać procedurę „ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML”.

W tej procedurze wyjaśniono sposób modyfikowania konfiguracji formatu raportowania elektronicznego (ER) przez ponowne zastosowanie szablonu programu Microsoft Excel, który został zmodyfikowany. W tej procedurze zaimportujesz zmodyfikowany szablon programu Excel do konfiguracji formatu raportowania elektronicznego, które zostały utworzone dla przykładowej firmy Litware, Inc., a następnie wygenerujesz dokumenty elektroniczne. Ta procedura jest przeznaczona dla użytkowników posiadających rolę administratora systemu lub dewelopera raportowania elektronicznego. Kroki można wykonać przy użyciu zestawu danych firmy GBSI. Przed rozpoczęciem pobierz i zapisz plik SampleVendPaymWsReport2.xlsx, która jest wyświetlany w temacie Pomocy Modyfikowanie formatu raportowania elektronicznego przez ponowne zastosowanie szablonu programu Microsoft Excel Excel (modify-electronic-reporting-format-reapply-excel-template/).

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego.  

## <a name="select-the-er-format"></a>Wybieranie formatu ER
1. Kliknij opcję Konfiguracje raportowania.
2. W drzewie rozwiń „model płatności”.
3. W drzewie zaznacz węzeł „Model płatności\Przykładowy raport arkusza”.
4. Kliknij opcję Załączniki.
    * Należy zauważyć, że plik programu Excel SampleVendPaymWsReport.xlsx jest aktualnie używany jako szablon do przetwarzania arkusza płatności.   
5. Kliknij przycisk Otwórz.
    * Kliknij przycisk Otwórz, aby obejrzeć układ szablonu programu Excel.  
    * Przejrzyj szablon. Należy zauważyć, że obecnie zawiera on następujące dane dla każdego wiersza płatności: numer konta dostawcy, nazwa dostawcy, bank, kod banku, numer konta, saldo winien, saldo ma i waluta. W tym przykładzie chcemy poszerzyć tę listę, dodając szczegóły daty płatności.   
6. Zamknij stronę.

## <a name="reapply-a-new-excel-template-to-er-format"></a>Ponownie stosowanie nowego szablonu programu Excel do formatu ER
1. Kliknij przycisk Konstruktor.
    * Otwórz wersję roboczą wybranego formatu ER w celu edytowania.  
2. W okienku akcji kliknij pozycję Importuj.
3. Kliknij opcję Aktualizacja z programu Excel.
    * Kliknij przycisk „Aktualizuj szablon”, a następnie zaznacz plik SampleVendPaymWsReport2.xlsx.  
    * Kliknij przycisk Aktualizuj szablon i przejdź do pobranego wcześniej pliku SampleVendPaymWsReport2.xlsx.  
4. Kliknij przycisk OK.
    * Szablon SampleVendPaymWsReport2.xlsx zostanie zastosowany. Struktura formatu ER zostanie zsynchronizowana z zawartością szablonu, którego elementy zostaną dodane do formatu ER. Wszelkie istniejące elementy w formacie ER, które nie są umieszczone w szablonie, zostaną usunięte z definicji formatu.  
5. W drzewie zaznacz element „Excel”.
    * Należy zwrócić uwagę, że teraz pole Szablon zawiera odwołanie do nowego szablonu.   
6. Kliknij opcję Załączniki.
7. Kliknij przycisk Otwórz.
    * Kliknij przycisk Otwórz, aby obejrzeć układ zmodyfikowanego szablonu programu Excel.  
    * Przejrzyj szablon. Należy zauważyć, że teraz zawiera wiersz daty płatności.   
8. Zamknij stronę.
9. W drzewie rozwiń węzeł „Excel”.
10. W drzewie rozwiń węzeł „Excel\PaymLines”.
11. W drzewie zaznacz element „Excel\PaymLines\PaymDate”.
    * Należy zauważyć, że format ER teraz zawiera jeden element więcej. Do szablonu programu Excel została dodana komórka PaymDate.  
12. Kliknij kartę Mapowanie.
13. W drzewie rozwiń model„”
14. W drzewie rozwiń węzeł „model\Płatności”.
15. W drzewie zaznacz element „model\Płatności\Data transakcji(TransactionDate)”.
16. Kliknij opcję Powiąż.
    * Określ, jakie dane będą dodawane do nowej komórki w czasie wykonywania.  
17. Kliknij przycisk Zapisz.
18. Zamknij stronę.

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a>Włączanie używania zmodyfikowanej wersji roboczej formatu ER w przetwarzaniu arkusza płatności
1. W okienku akcji kliknij pozycję Konfiguracje.
2. Kliknij opcję Parametry użytkownika.
3. W polu Ustawienia uruchamiania wybierz opcję Tak.
4. Kliknij przycisk OK.
5. Kliknij przycisk Edytuj.
6. W polu Uruchom wersję roboczą wybierz opcję Tak.

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a>Używanie zmodyfikowanej wersji roboczej formatu ER w przetwarzaniu arkusza płatności
    * Przejrzyj utworzony arkusz, w tym nowy szczegół wierszy płatności — datę płatności.  


