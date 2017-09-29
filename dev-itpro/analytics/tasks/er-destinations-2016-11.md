--- 
title: Konfigurowanie lokalizacji docelowych na potrzeby raportowania elektronicznego (ER)
description: "Ta procedura przedstawia sposób konfigurowania i używania różnych miejsc docelowych dla składników wyjściowych raportowania elektronicznego (ER), takich jak folder lub plik."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 88927a220246d11e48b210eb5648d7e7c2a7cef8
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="configure-destinations-for-electronic-reporting-er"></a>Konfigurowanie lokalizacji docelowych na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przedstawia sposób konfigurowania i używania różnych miejsc docelowych dla składników wyjściowych raportowania elektronicznego (ER), takich jak folder lub plik. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF. Niemcy to kraj\region podstawowego adresu firmy, jednak w tej procedurze można użyć dowolnej firmy. 

Formatem używanym w tym przykładzie jest Polecenie przelewu ISO20022, ale można użyć dowolnego innego formatu, który został już zaimportowany. Należy zauważyć, że ta procedura jest przykładem konfiguracji z jednym plikiem i jednym miejscem docelowym. Więcej informacji na temat zarządzania miejscami docelowymi raportowania elektronicznego można znaleźć na stronach wiki Pomocy programu Dynamics 365 for Finance and Operations.

1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Aplikacja docelowa raportowania elektronicznego.
2. Kliknij przycisk Nowy, aby utworzyć nowy zbiór miejsc docelowych dla formatu.
3. W polu Odwołanie zaznacz format, dla którego chcesz skonfigurować miejsca docelowe.
    * Jeśli nie masz wartości do wybrania, oznacza to, że nie zaimportowano żadnych konfiguracji formatów raportowania elektronicznego. Należy zaimportować konfigurację formatu przed skonfigurowaniem miejsc docelowych.  
4. Kliknij przycisk Nowy, aby utworzyć nowe miejsce docelowe dla plików.
    * Należy zauważyć, że można utworzyć jedno miejsce docelowe plików dla każdego składnika wyjściowego o takim samym formacie, takiego jak folder lub plik. Miejsca docelowe będzie można osobno włączać i wyłączać w ustawieniach.  
5. W polu Nazwa wprowadź przyjazną nazwę składnika wyjściowego.
    * Zaleca się używanie sugestywnych nazw, na przykład „Plik płatności” lub „Raport z kontroli”. Te nazwy będą prezentowane użytkownikom podczas konfigurowania razem z ustawieniami miejsc docelowych.  
6. W polu Nazwa pliku wybierz plik lub folder specyficzny dla formatu.
7. Kliknij przycisk Ustawienia.
8. W polu Włączone wybierz opcję Tak.
    * Pole wyboru Włączone na każdej karcie pozwala włączać i wyłączać osobno każde miejsce docelowe. W tym przykładzie włączysz wysyłanie pliku wyjściowego do adresata poczty podczas generowania pliku.  
9. Kliknij przycisk Edytuj, aby skonfigurować adresatów wiadomości e-mail.
10. Kliknij przycisk Dodaj.
11. Kliknij opcję Wiadomość e-mail zarządzania drukowaniem.
12. W polu Źródło poczty e-mail wybierz opcję.
    * Można wybrać różne typy źródeł poczty e-mail, takie jak typ odbiorcy lub dostawcy. Określa to typ argumentu, który będzie zwracany przez formułę konta źródła poczty e-mail. Formuła konta źródła poczty e-mail, opisana w następnym kroku, służy do powiązania źródła wiadomości e-mail. Wybierz opcję Dostawca, jeśli formuła będzie zwracała konto dostawcy. Użyj opcji Dostawca, jeśli używasz przykładu konfiguracji przelewu bankowego ISO 20022.  
13. Kliknij przycisk Powiąż źródło poczty e-mail.
14. W formule wprowadź specyficzne dla dokumentu odwołanie do wybranego wcześniej typu strony.
    * Zamiast wpisywać informacje ręcznie, można odszukać węzeł źródła danych reprezentujący konto strony, a następnie kliknąć przycisk Dodaj źródło danych, aby zaktualizować formułę. Na przykład: W przypadku konfiguracji polecenia przelewu ISO 20022 węzłem reprezentującym konto dostawcy jest „$PaymentsForCoveringLetter”.Wierzyciel.Identyfikator.SourceID. W przeciwnym razie wpisz dowolny ciąg tekstowy, np. „DE-001”, aby zapisać formułę.  
15. Kliknij przycisk Zapisz.
16. Zamknij stronę.
17. Kliknij przycisk Edytuj, aby skonfigurować dane osoby kontaktowej dla strony.
18. W polu Kontakt podstawowy wybierz opcję Tak.
    * Można użyć różnych opcji w celu wskazania, jaki typ kontaktu strony powinien być używany jako adres e-mail dla tego miejsca docelowego. W tym przykładzie korzystamy z głównej osoby kontaktowej.  
19. Kliknij przycisk OK.
20. Kliknij przycisk OK.
21. W polu Temat wpisz wartość.
22. Kliknij przycisk OK.

