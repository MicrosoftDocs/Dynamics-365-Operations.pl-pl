---
title: Rejestrowanie przyjęcia zwróconych towarów
description: Przyjęcie zwróconych towarów można zarejestrować za pomocą formularza Przegląd przyjęć lub Rejestracja.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08a40d7e95ffb17a096f759b332e77aeaf96ffd6
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742267"
---
# <a name="register-the-receipt-of-returned-items"></a>Rejestrowanie przyjęcia zwróconych towarów 

[!include [banner](../includes/banner.md)]


Istnieją dwie metody rejestrowania przyjęcia zwróconych towarów. Pierwsza metoda to proces przyjęcia w magazynie, w którym należy użyć formularza **Przegląd przyjęć**. Druga metoda korzysta z formularza **Rejestracja**.

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>Rejestrowanie zwróconych towarów za pomocą formularza Przegląd przyjęć

Za pomocą formularza **Przegląd przyjęć** można zidentyfikować wysyłkę zwrotną według numeru autoryzacji zwrotu (RMA). Jeśli nazwa arkusza jest zdefiniowana na karcie **Ustawienia** i istnieją wiersze arkusza, które odpowiadają wierszom wybranym w formularzu **Przegląd przyjęć**, nowy nagłówek arkusza jest tworzony po kliknięciu przycisku **Rozpocznij przyjęcie**.

1.  Wybierz kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Przegląd przyjęć**.

2.  W polu **Nazwa konfiguracji** zaznacz opcję **Zamówienie zwrotu**, a następnie kliknij przycisk **Aktualizuj**.
    

    > [!TIP]
    > <P>Wprowadzając odpowiednie dane w polach <STRONG>Zakres</STRONG>, można ograniczyć liczbę wyników wyszukiwania. Aby uzyskać dokładny wynik, w polu <STRONG>Numer autoryzacji zwrotu</STRONG> można wpisać lub wybrać numer RMA. Aby zdefiniować i zapisać zestaw filtrów ograniczających wyświetlanie przywozów, kliknij kartę <STRONG>Ustawienia</STRONG>. Dostępne filtry obejmują typy, magazyny i doki.</P>

    

    > [!WARNING]
    > <P>Zamówień zwrotu nie można mieszać z innymi typami przyjęć w formularzu <STRONG>Przegląd przyjęć</STRONG>. Dlatego odniesieniem będzie zawsze zamówienie sprzedaży, ale brak identyfikatora zamówienia sprzedaży zostanie określony w nagłówku arkusza.</P>



3.  W siatce **Przyjęcia** znajdź wiersz odpowiadający zwracanemu towarowi, a następnie zaznacz pole wyboru w kolumnie **Zaznacz do przyjęcia**.

4.  Aby wykluczyć określone wiersze z pokwitowania zwrotu, na przykład towary z pierwotnego zamówienia, które nie znalazły się w wysyłce zwrotnej, wyczyść odpowiednie pola wyboru **Zaznacz do przyjęcia** w tabeli **Wiersze** w dolnej części formularza.

5.  Kliknij przycisk **Rozpocznij przyjęcie**, aby skonfigurować arkusz przyjęć.
    

    > [!NOTE]
    > <P>W programie można zaznaczyć wiele zwrotów zamówień i uwzględnić je wszystkie w jednym procesie przyjęcia towaru. Każdy wiersz zwrotu zamówienia zostanie skopiowany do odpowiedniego wiersza arkusza przyjęcia towaru.</P>

    

    > [!NOTE]
    > <P>Można także ręcznie utworzyć arkusz przywozu za pomocą formularza <STRONG>Przyjęcie pozycji</STRONG>. 



6.  Wybierz kolejno opcje **Zarządzanie zapasami** \> **Arkusze** \> **Przyjęcie pozycji** \> **Przyjęcie pozycji**.

7.  Wybierz arkusz przywozu, który został właśnie utworzony, a następnie kliknij przycisk **Wiersze**, aby otworzyć formularz **Wiersze arkusza, lokalizacje**.

8.  Na karcie **Ogólne** dostosuj liczbę w polu **Ilość**, jeśli jest to wymagane, a następnie przypisz kod dyspozycji w polu **Kod dyspozycji**.
    
    Alternatywnie można zaznaczyć pole wyboru **Zarządzanie kwarantanną**, aby zwracane towary przechodziły proces inspekcji w kontekście zlecenia kwarantanny.
    

    > [!NOTE]
    > <P>Jeśli wyślesz zwracane towary do kwarantanny, nie można określić kodu dyspozycji.</P>



9.  Kliknij przycisk **Weryfikuj**.

10. Jeśli w procesie sprawdzania poprawności nie występują błędy, kliknij opcję **Księguj**.

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>Zarejestruj zwrócone towary za pomocą formularza rejestracji

Jako alternatywy do korzystania z formularza **Przegląd przyjęć** można użyć formularza **Rejestracja**, aby zarejestrować przywóz zwracanych towarów.

1.  Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**. Utwórz nowe zamówienie zwrotu lub otwórz zamówienie zwrotu z listy. Na skróconej karcie **Wiersze** wybierz wiersz zamówienia zwrotu. Kliknij opcję **Aktualizuj wiersz**, a następnie opcję **Rejestracja**.

2.  Przypisz kod dyspozycji w polu **Kod dyspozycji**, a następnie kliknij przycisk **OK**.
    

    > [!NOTE]
    > <P>Nie można wysłać towaru do celów inspekcji jako zlecenia kwarantanny, korzystając z formularza <STRONG>Rejestracja</STRONG>.</P>



3.  W siatce **Transakcje** wybierz transakcję do zarejestrowania.

4.  W siatce **Rejestruj teraz** kliknij przycisk **Dodaj**. Powtarzaj poprzednie dwa kroki, dopóki wszystkie zwrócone towary nie będą wyświetlane w siatce **Rejestruj teraz**.

5.  Kliknij przycisk **Zaksięguj wszystkie**.

## <a name="see-also"></a>Informacje dodatkowe

[Przegląd przyjęć (formularz)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))

  


