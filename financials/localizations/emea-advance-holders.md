---
title: Posiadacze zaliczek
description: "Więcej informacji na temat funkcji posiadacza zaliczki w Microsoft Dynamics 365 dla operacji."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262574
ms.assetid: 87924785-6032-4125-8279-5b1a758f4d80
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 8cfe98e3859778e4fdc61f22b437cb1b4d004549
ms.lasthandoff: 03/31/2017


---

# <a name="advance-holders"></a>Posiadacze zaliczek

Więcej informacji na temat funkcji posiadacza zaliczki w Microsoft Dynamics 365 dla operacji.

*Posiadacza zaliczki* jest pracownikiem firmy, który jest odpowiedzialny za kwotę wydatków, dostarczonego przez organizację. Tylko pracownik firmy może być posiadaczem zaliczki. W przypadku zamówień posiadacz zaliczki raporty do firmy o wydatki, które zostały wprowadzone. Firma prowadzony pracownika dla kwoty wydatków. Spółka kontroluje równowagi dla każdego posiadacza zaliczki. Użytkownicy w firmach w Estonii, Łotwy, Litwy, Polski, Republiki Czeskiej, Węgier i Rosji może odzwierciedlać określonych transakcji towarzyszących operacji z pracowników firmy, którzy są odpowiedzialni za kwotę wydatków, dostarczonego przez organizację.

## <a name="set-up-an-advance-holder"></a>Konfigurowanie posiadacz zaliczki
Aby skonfigurować posiadacz zaliczki, następujące zadania powinny zostać dokonane w kolejności.
1.  Utwórz grupy posiadaczy zaliczek.
2.  Konfigurowanie profilu księgowania pracownika.
3.  Ustaw parametry płatne konta.
4.  Utwórz szczególne warunki płatności dla posiadacza zaliczki.
5.  Utwórz posiadacz zaliczki.

### <a name="advance-holder-groups"></a>Grupy posiadaczy zaliczek

Użyj **grupy posiadaczy zaliczek** stronę, aby utworzyć grupę posiadacza zaliczki. Można określić nazwę, opis i konto przeciwstawne dla grupy posiadacza zaliczki.
### <a name="employee-posting-profile"></a>Profil księgowania pracownika

Użyj **profilów księgowania pracownika** stronę, aby utworzyć profil dla transakcje posiadaczy zaliczek. Można określić następujące informacje dla profilu księgowania pracownika.
|Pole |opis|
|------|-----------|
|Profil księgowania|Wprowadź kod identyfikacyjny profilu księgowania dla posiadacza zaliczek.|
|opis|Wprowadź krótki opis profilu księgowania.|
|Ważny dla|Wybierz jedną z następujących opcji dla poziomu grupowania do definiowania profilu księgowania: 
**Tabela** — ta opcja służy do konfigurowania profilu księgowania dla posiadacza jedną zaliczek. Należy podać kod posiadacza zaliczki w polu odwołanie.
**Grupa** — ta opcja służy do konfigurowania profilu księgowania dla grupy posiadaczy zaliczek. Należy podać kod grupy w polu odwołanie.
**Wszystkie** — ta opcja służy do konfigurowania profilu księgowania dla wszystkich posiadaczy zaliczek. | | Odwołanie | Wybierz kod posiadacza zaliczki, jeśli została wybrana opcja Tabela w polu Ważny dla pola lub wybierz grupę posiadacza zaliczki, jeśli grupa jest zaznaczona w polu Ważny dla pola. | | Konto rozrachunkowe | Wybierz konto rozrachunkowe dla księgowania transakcji. |



### <a name="account-payable-parameters"></a>Parametry konta płatne

Aby uwzględnić transakcje posiadacza zaliczki należy zdefiniować następujące czynności na **parametry płatne konta** strony **posiadacze zaliczek** sekcji.
|                                                |                   |
|------------------------------------------------|-------------------|
|  **Field**                                     | **Description**                                                                                                                                                                  |
| **Posting profile**                            | Wybierz domyślny profil, aby zrealizować transakcje posiadaczy zaliczek.                                                                                                         |
| **Advance holder sorting**                     | Jeśli zaznaczone, posiadacze zaliczek pojawi się na początku listy w **posiadacze zaliczek** strony.                                                                     |
| **Issue when balance is open**                 | Jeśli zaznaczone, będą mogły problem zaliczek na posiadacza zaliczki, który ma otwarte saldo dodatnie.                                                                      |
| **Saldo zamknięcia za pomocą środków pieniężnych grupy pól: Nazwa** | Wybierz kod arkusza dokumentu dostawy środków pieniężnych. Ten kod arkusza jest używany do generowania dokumenty kW i KP podczas zamykania salda posiadacza zaliczki za pośrednictwem środków pieniężnych. |
| **Cash**                                       | Wybierz konto kasowe, aby ustalić załączników, które są używane do zamykania sald dla posiadacza zaliczek.                                                                 |
| **Saldo zamknięcia za pośrednictwem banku grupy pól: Nazwa** | Wybierz kod arkusza transakcji zamknąć salda za pośrednictwem banku.                                                                                                   |
| **Account type**                               | Wybierz bank, aby zamknąć sald dla posiadacza zaliczek za pośrednictwem banku.                                                                                                        |
| **Main account**                               | Wybierz kod konta bankowego, aby zamknąć sald dla posiadacza zaliczek za pośrednictwem banku.                                                                                           |

### <a name="terms-of-payment-for-advance-holder"></a>Warunki płatności dla posiadacza zaliczki

Aby poprawnie zarejestrować i zaksięgować zamówienie zakupu za pośrednictwem posiadacz zaliczki, należy użyć warunki płatności, który został skonfigurowany z **od posiadacza zaliczki** ustawioną opcję **True**.
### <a name="create-an-advance-holder-creation"></a>Utwórz tworzenie posiadacza zaliczki

Przed utworzeniem posiadacz zaliczki musi już zdefiniowano pracowników. Aby uzyskać więcej informacji, zobacz [wprowadź informacje o pracowniku (Przewodnik zadania).](http://ax.help.dynamics.com/en/wiki/enter-worker-information/) Użyj **posiadacze zaliczek** stronę, aby zdefiniować pracownika jako posiadacz zaliczki. Wybierz pracownika, jako posiadacz zaliczki, kliknij **edytować**, a następnie ustaw **posiadacza zaliczki** opcji w celu **True**. Konieczne jest także wypełnienie pola.
|                |                                                                                             |
|----------------|---------------------------------------------------------------------------------------------|
| **Field**      | **Description**                                                                             |
| **Group**      | Wybierz grupę posiadacza zaliczki.                                                             |
| **Series**     | Umożliwia wprowadzenie serii dokumentu, który jest używany do weryfikacji tożsamości posiadacza zaliczki. |
| **Number**     | Należy wprowadzić numer dokumentu, który jest używany do weryfikacji tożsamości posiadacza zaliczki. |
| **Issue date** | Wybierz lub wprowadź daty wydania dokumentu.                                                    |
| **Issued by**  | Wprowadź szczegóły organ lub osoba, która wydała dokument.                       |

## <a name="advance-holder-inquiries-and-reports"></a>Zaliczki posiadacz zapytania i raporty
### <a name="advance-holder-transactions-inquiry"></a>Zapytanie transakcje posiadacza zaliczki

Aby uzyskać listę transakcji dla posiadacz zaliczki, kliknij przycisk **transakcji** znajdującego się na **posiadacze zaliczek** strony. Wyświetlanie transakcji dla wszystkich posiadacze zaliczek lub aby utworzyć określone na podstawie transakcji posiadaczy zaliczek zapytanie, kliknij przycisk **rozrachunków z dostawcami**&gt;**zapytania i raporty**&gt;**z góry posiadaczy zapytania i raporty**&gt; transakcji. Kliknij **załącznika** otworzyć **transakcje na załączniku** strony.
### <a name="advance-holder-balance-inquiry"></a>Zapytanie Saldo posiadacza zaliczki

Aby wyświetlić saldo dla posiadacz zaliczki, użyj **posiadacze zaliczek** strony. Aby wyświetlić salda wszystkich posiadacze zaliczek lub aby utworzyć określone na podstawie kont posiadaczy zaliczek zapytanie, kliknij przycisk **rozrachunków z dostawcami**&gt;**zapytań i raportów**&gt;**z góry posiadaczy zapytania i raporty**&gt;**saldo.**
### <a name="advance-holder-balance-report"></a>Raport salda posiadacza zaliczki

Kliknij, aby wyświetlić podgląd i drukowanie raportu na podstawie informacji o saldo posiadaczy zaliczek **rozrachunków z dostawcami**&gt;**informacji i raportów**&gt;**z góry posiadaczy zapytania i raporty**&gt;**raportu salda posiadacza zaliczki**.
### <a name="advance-holder-transactions-report"></a>Raport transakcji posiadacza zaliczki

Kliknij, aby wyświetlić podgląd i drukowanie raportu na podstawie transakcji posiadaczy zaliczek **rozrachunków z dostawcami**&gt;**informacji i raportów**&gt;**z góry posiadaczy zapytania i raporty**&gt;**raportu transakcji posiadacza zaliczki**.



<a name="see-also"></a>Informacje dodatkowe
--------

[Advance holder transactions](emea-advance-holders-transactions.md)


