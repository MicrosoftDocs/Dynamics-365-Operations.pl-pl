--- 
title: "Konfigurowanie formatu dokumentu płatności dla faktur projektu"
description: "Firmy zazwyczaj dołączają drukowane dokumenty płatności do faktur, aby pomóc klientom i dostarczyć referencyjne informacje płatnicze na potrzeby księgowania i rozliczania."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 02/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 8afbcf781e917f48136e06692234d49302b077fb
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="set-up-payment-slip-format-for-project-invoices"></a>Konfigurowanie formatu dokumentu płatności dla faktur projektu

[!include[task guide banner](../../includes/task-guide-banner.md)]

Firmy zazwyczaj dołączają drukowane dokumenty płatności do faktur, aby pomóc klientom i dostarczyć referencyjne informacje płatnicze na potrzeby księgowania i rozliczania. Dokument płatności mogą towarzyszyć nie tylko fakturom sprzedaży i fakturom niezależnym, ale także fakturom za projekty i usługi, ponagleniom, notom odsetkowym i wyciągom z konta. Aby przetwarzać dokumenty płatności, należy najpierw skonfigurować numer identyfikacyjny wierzyciela oraz formaty załączanych dokumentów płatności.

Ta procedura wykorzystuje firmę demonstracyjną DEMF. 

Ta funkcja jest dostępna w firmach, których adresem podstawowym jest Dania.


## <a name="set-up-a-creditor-id-number"></a>Konfigurowanie numeru identyfikacyjnego wierzyciela
1. Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Firmy.
2. Rozwiń lub zwiń sekcję Informacje o koncie bankowym.
3. Kliknij przycisk Edytuj.
4. W polu Identyfikator wierzyciela FI wpisz wartość.
5. Kliknij przycisk Zapisz.
6. Zamknij stronę.

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a>Konfigurowanie formatu dokumentu płatności dla faktur, not, pism i wyciągów
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia > Formularze > Ustawienia formularza.
2. Kliknij kartę Faktura.
3. W polu Załącznik powiązanych płatności faktury dla odbiorcy wybierz opcję.
    * Brak — Dokument płatności nie jest drukowany. Zaznacz tę opcję, jeśli kwota płatności jest w walucie innej niż duńska korona (DKK).   FIK 751 — Drukowanie dokumentu płatności FIK 751, gdy kwota płatności i termin płatności mają być wpisane ręcznie do dokumentu płatności.   FIK 752 — Zostanie wydrukowany dokument płatności FIK 752, jeśli ma być używany generowany komputerowo dokument z nadrukiem terminu i kwoty płatności.  
4. Kliknij przycisk Zapisz.
5. Kliknij kartę Faktura niezależna.
6. W polu Załącznik powiązanych płatności faktury niezależnej wybierz opcję.
    * Brak — Dokument płatności nie jest drukowany. Zaznacz tę opcję, jeśli kwota płatności jest w walucie innej niż duńska korona (DKK).   FIK 751 — Drukowanie dokumentu płatności FIK 751, gdy kwota płatności i termin płatności mają być wpisane ręcznie do dokumentu płatności.   FIK 752 — Zostanie wydrukowany dokument płatności FIK 752, jeśli ma być używany generowany komputerowo dokument z nadrukiem terminu i kwoty płatności.  
7. Kliknij przycisk Zapisz.
8. Kliknij kartę Nota odsetkowa.
9. W polu Załącznik powiązanych płatności noty odsetkowej wybierz opcję.
    * Brak — Dokument płatności nie jest drukowany. Zaznacz tę opcję, jeśli kwota płatności jest w walucie innej niż duńska korona (DKK).   FIK 751 — Drukowanie dokumentu płatności FIK 751, gdy kwota płatności i termin płatności mają być wpisane ręcznie do dokumentu płatności.   FIK 752 — Zostanie wydrukowany dokument płatności FIK 752, jeśli ma być używany generowany komputerowo dokument z nadrukiem terminu i kwoty płatności.  
10. Kliknij przycisk Zapisz.
11. Kliknij kartę Ponaglenie.
12. W polu Załącznik powiązanych płatności dla ponaglenia wybierz opcję.
    * Brak — Dokument płatności nie jest drukowany. Zaznacz tę opcję, jeśli kwota płatności jest w walucie innej niż duńska korona (DKK).   FIK 751 — Drukowanie dokumentu płatności FIK 751, gdy kwota płatności i termin płatności mają być wpisane ręcznie do dokumentu płatności.   FIK 752 — Zostanie wydrukowany dokument płatności FIK 752, jeśli ma być używany generowany komputerowo dokument z nadrukiem terminu i kwoty płatności.  
13. Kliknij przycisk Zapisz.
14. Kliknij kartę Wyciąg z konta.
15. W polu Załącznik powiązanych płatności na wyciągu z konta wybierz opcję.
    * Brak — Dokument płatności nie jest drukowany. Zaznacz tę opcję, jeśli kwota płatności jest w walucie innej niż duńska korona (DKK).   FIK 751 — Drukowanie dokumentu płatności FIK 751, gdy kwota płatności i termin płatności mają być wpisane ręcznie do dokumentu płatności.   FIK 752 — Zostanie wydrukowany dokument płatności FIK 752, jeśli ma być używany generowany komputerowo dokument z nadrukiem terminu i kwoty płatności.  
16. Kliknij przycisk Zapisz.
17. Zamknij stronę.


