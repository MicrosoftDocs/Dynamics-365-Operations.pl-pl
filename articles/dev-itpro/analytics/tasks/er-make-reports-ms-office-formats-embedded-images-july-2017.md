--- 
title: "Projektowanie konfiguracji służących do generowania raportów w formatach pakietu Microsoft Office z osadzonymi obrazami"
description: "Etapy w tym temacie zawierają informacje o sposobie projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentów elektronicznych w formatach pakietu Microsoft Office (Excel i Word) zawierających osadzone obrazy."
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5e3ba5c76df3dcc5042074a565d102ceaeeadfb0
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="design-configurations-to-generate-reports-in-microsoft-office-formats-with-embedded-images"></a>Projektowanie konfiguracji służących do generowania raportów w formatach pakietu Microsoft Office z osadzonymi obrazami

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Aby wykonać kroki podane w tej procedurze, należy najpierw wykonać procedurę „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”. W tej procedurze wyjaśniono sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentów programów Microsoft Excel i Microsoft Word zawierających osadzone obrazy. W tej procedurze utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Kroki można wykonać przy użyciu zestawu danych firmy USMF. Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. Zanim rozpoczniesz, pobierz i zapisz pliki wymienione w temacie pomocy [Osadzanie obrazów i kształtów w dokumentach biznesowych generowanych przy użyciu narzędzia Raportowanie elektroniczne](../electronic-reporting-embed-images-shapes.md). Pliki to: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png i Cheque template Word.docx.

## <a name="verify-prerequisites"></a>Sprawdzanie wymagań  
 1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.  
 2. Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.   
 3. Kliknij opcję Konfiguracje raportowania.  
 
## <a name="add-a-new-er-model-configuration"></a>Dodawanie nowej konfiguracji modelu ER  
 1. Zamiast tworzyć nowy model, można załadować plik konfiguracji modelu ER (Model for cheques.xml), który został wcześniej zapisany. Plik ten zawiera przykładowy model danych dla czeków płatniczych i mapowanie modelu danych do składników danych aplikacji Dynamics 365 for Operations.   
 2. Na skróconej karcie Wersje kliknij przycisk Import/eksport.   
 3. Kliknij opcję Załaduj z pliku XML.  
 4. Kliknij przycisk Przeglądaj, a następnie wybierz plik Model for cheques.xml.   
 5. Kliknij przycisk OK.  
 6. Załadowany model zostanie użyty jako źródło danych informacji do generowania dokumentów, które zawierają obrazy w programie Excel i Word.  

## <a name="add-a-new-er-format-configuration"></a>Dodawanie nowej konfiguracji formatu ER  
 1. Zamiast tworzyć nowy format można załadować plik konfiguracji formatu ER (Cheques printing format.xml), który został wcześniej zapisany. Ten plik zawiera przykładowy układ formatu do drukowania czeków przy użyciu wstępnie zadrukowanego formularza i mapowanie tego formatu do modelu danych „Model for cheques”.   
 2. Kliknij opcję Import/eksport.  
 3. Kliknij opcję Załaduj z pliku XML.  
 4. Kliknij przycisk Przeglądaj i wybierz plik Cheques printing format.xml.   
 5. Kliknij przycisk OK.  
 6. W drzewie rozwiń węzeł „Model czeków”.  
 7. W drzewie zaznacz element „Model czeków\Format drukowania czeków”.  
 8. Załadowany format zostanie użyty do generowania dokumentów, które zawierają obrazy w programie Excel i Word.   

## <a name="configure-er-user-parameters"></a>Konfigurowanie parametrów użytkownika modułu ER  
 1. W okienku akcji kliknij pozycję Konfiguracje.  
 2. Kliknij opcję Parametry użytkownika.  
 3. W polu Ustawienia uruchamiania wybierz opcję Tak.  
  Włącz flagę „Uruchom projekt”, aby uruchomić wersję roboczą wybranego formatu zamiast wersji ukończonej.  
 4. Kliknij przycisk OK.  

## <a name="configure-cash--bank-management-parameters"></a>Konfigurowanie parametrów modułu Zarządzanie gotówką i bankami  
 1. Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.  
 2. Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „USMF OPER”.  
 3. W okienku akcji kliknij pozycję Konfiguracja.  
 4. Kliknij przycisk Sprawdź.  
 5. Rozwiń sekcję Ustawienia.  
 6. Kliknij przycisk Edytuj.  
 7. W polu Logo firmy wybierz opcję Tak.  
 8. Kliknij Logo firmy.  
 9. Kliknij przycisk Zmień.  
 10. Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Company logo.png.   
 11. Kliknij przycisk Zapisz.  
 12. Zamknij stronę.  
 13. Rozwiń sekcję Podpis.  
 14. W polu Drukuj pierwszy podpis zaznacz opcję Tak.  
 15. Kliknij przycisk Zmień.  
 16. Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Signature image.png.   
 17. Rozwiń sekcję Kopie.  
 18. W polu Znak wodny wybierz opcję.  
 19. W polu Ogólny elektroniczny format eksportu wybierz opcję Tak.  
 20. Wybierz konfigurację „Cheques printing form”.  
 21. Teraz wybrany format ER zostanie użyty do drukowania czeków.  
 22. Kliknij opcję Dołącz.  
 23. Kliknij przycisk Nowy.  
 24. Kliknij opcję Plik.  
 25. Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Signature image 2.png.   
 26. Zamknij stronę.  
 27. Zamknij stronę.  
 28. Zamknij stronę.  
 29. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.  
 30. W polu Zezwalaj na tworzenie przelewu testowego dla nieaktywnych kont bankowych zaznacz opcję Tak.  
 31. Kliknij przycisk Zapisz.  
 32. Zamknij stronę.  

