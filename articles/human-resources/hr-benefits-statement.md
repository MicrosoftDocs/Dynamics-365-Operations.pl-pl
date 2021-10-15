---
title: Zestawienie świadczeń
description: W raporcie Sprawozdanie o świadczeniach wyjaśniono świadczenia, na które jest zarejestrowany pracownik.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 46f7358684502a4bf05854fbcb5cca9a1eb2c87c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548062"
---
# <a name="benefit-statement"></a>Zestawienie świadczeń

Raport **Oświadczenie o korzyściach** zawiera zestawienie świadczeń, na które pracownik jest obecnie zapisany. Dostęp do raportu ma bezpośrednio pracownik lub administrator świadczeń. W **sprawozdaniu o świadczeniach** jest wyświetlona lista zarejestrowanych świadczeń, opcji świadczenia, kosztów oraz wszystkich zarejestrowanych osób na utrzymaniu pracownika lub beneficjentów. Oświadczenie można wydrukować dla jednego pracownika lub wielu pracowników.

> [!NOTE]
Funkcja **Oświadczenie o korzyściach** musi być włączona w obszarze roboczym **Zarządzanie funkcjami**. W tym celu należy włączona funkcja **Zarządzanie świadczeniami** w zarządzaniu funkcjami. 


## <a name="importing-the-benefit-statement"></a>Importowanie zestawienia świadczeń 

Aby można było korzystać z **zestawienia świadczeń**, należy zaimportować **zestawienie świadczeń** za pomocą konfiguracji raportu. Aby to zrobić, wykonaj następujące czynności:

1.  Przejdź do obszaru roboczego **Administrowanie systemem**.

2.  Wybierz kafelek **Raportowanie elektroniczne**.

3.  Przejdź do **dostawców konfiguracji** i wybierz **repozytoria**.

  ![Wybór repozytoriów.](https://user-images.githubusercontent.com/26801678/134203290-7faf7245-ed08-44e9-95a1-a7ba278c42c6.png)

4.  Wybierz **z listy zasoby ludzkie**, a następnie **otwórz**.

    ![Repozytoria konfiguracji.](https://user-images.githubusercontent.com/26801678/134203619-b3fd087d-1fe9-45ef-a588-1afedfe38dfd.png)

5.  Wybierz model **zestawienia świadczeń** w lewym okienku i rozwiń go w taki sposób, aby został wyświetlony **format zestawienia świadczeń**.

6.  Wybierz **format sprawozdania o świadczeniach** w lewym okienku.

7.  Po prawej stronie ekranu pojawi się skrócona karta **Wersje**. Wybierz opcję **Importuj**.

    ![Skrócona karta Wersje.](https://user-images.githubusercontent.com/26801678/134203763-f12ef549-e326-400d-ac69-b25fc94af47b.png)

## <a name="generate-the-benefit-statement-as-a-pdf-file"></a>Generuj oświadczenie o świadczeniach jako plik PDF

Domyślnie dokument **wyciągu świadczenia** jest dokumentem Microsoft Word. Aby drukować w formacie PDF, musisz skonfigurować opcję PDF w aplikacji **docelowej raportowania elektronicznego**. 

1. W tym celu przejdź do obszaru roboczego **Administrowanie systemem** > **Raportowanie elektroniczne** > **Powiązane linki** > **Aplikacja docelowa raportowania elektronicznego**.

1.  Wybierz pozycję **Nowy**.

2.  W polu **Odniesienia** wybierz format **format zestawienia świadczeń**.

3.  Na **skróconej karcie Plik docelowy** wybierz pozycję **Nowy**.

4.  W polu **nazwa** wprowadź **Zestawienie świadczeń (PDF)**.

5.  W polu **nazwa składnika pliku** wprowadź lub wybierz opcję **Zestawienie świadczeń**.

6.  Zaznacz pole **wyboru Konwertuj na plik PDF**.

7.  Wybierz **pozycję Ustawienia** z menu. 

    ![Miejsce docelowe pliku.](https://user-images.githubusercontent.com/26801678/134203881-a3f1ebc3-d816-485d-a53b-026cc29cae64.png)

8.  Wybierz **skróconą kartę Plik**, a następnie wybierz **opcję Włączone**.

9.  Kliknij przycisk **OK**.
   
> [!NOTE]
> Funkcja zarządzania korzyściami jest w stanie podglądu. Występuje znany problem podczas używania ustawienia docelowego adresu e-mail w raporcie **Aplikacja docelowa raportowania elektronicznego**. Możesz otrzymać komunikat o błędzie i wiadomość e-mail nie zostanie wysłana.

**Zestawienie świadczeń** można generować na następujących stronach:

-   **Obszar roboczy zarządzania świadczeniami** > **Łącza** > **Raporty** > **Zestawienie świadczeń**

-   **Pracownicy (forma dotychczasowa)** > **Zakładka Dane osobowe** > **Zestawienie świadczeń**

-   **Usprawnione wejście pracowników** > **Raport świadczeń** > **Zestawienie świadczeń**

-   **Samoobsługa pracowników** > **Świadczenia** > **Zobacz zestawienie świadczeń**

> [!NOTE]
>  Dostęp do **zestawienia świadczeń** w aplikacji **Samoobsługa pracownika** jest kontrolowany przez uprawnienie **Wyświetl zestawienie świadczeń**. To jest w ramach obowiązku **Świadczenia samoobsługowe dla pracowników**. To uprawnienie jest domyślnie przyznawane pracownikom.

## <a name="report-contents"></a>Zawartość raportu

W **sprawozdaniu o świadczeniach** zostaną wydrukowane potwierdzone wybory planu pracownika, w tym wszelkie plany, z których zrezygnowano. Poniższy obraz przedstawia przykład tego raportu. 

![Raport zestawienia świadczeń.](https://user-images.githubusercontent.com/26801678/134204058-61baa318-fede-4795-a256-acdf3217f9f9.png)

W raporcie będą wyświetlane **opcje Plan**, **Opcje pokrycia**, **Koszt pracownika** i **Koszt pracodawcy**. Raport będzie również zawierał listę wszystkich objętych ubezpieczeniem osób pozostających na utrzymaniu. Jeśli z planem są powiązani beneficjenci, zostaną wyświetleni beneficjenci i ich priorytet dystrybucji oraz procent.

Raport o **sprawozdaniu o świadczeniach** można wydrukować jednocześnie dla wielu pracowników przy użyciu skróconej karty **Rekordów do dołączenia** na stronie **Sprawozdanie o świadczeniach**.
