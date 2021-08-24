---
title: ER Konfigurowanie miejsc docelowych
description: Ta procedura przedstawia sposób konfigurowania i używania różnych miejsc docelowych dla składników wyjściowych raportowania elektronicznego (ER), takich jak folder lub plik.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERFormatDestinationTable, SysLookupPicklist, ERFormatDestinationSettings, ERFormatDestinationEmailSettings, ERExpressionDesignerFormula, SRSPrintDestinationTokens
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f1e679b52b28ff1ca117c5224fc7e2825feb26e5e5aea1c8b5bc3a88d1eaf235
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743270"
---
# <a name="er-configure-destinations"></a>ER Konfigurowanie miejsc docelowych

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób konfigurowania i używania różnych miejsc docelowych dla składników wyjściowych raportowania elektronicznego (ER), takich jak folder lub plik. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF. Niemcy to kraj\region podstawowego adresu firmy, jednak w tej procedurze można użyć dowolnej firmy. 

Formatem używanym w tym przykładzie jest Polecenie przelewu ISO20022, ale można użyć dowolnego innego formatu, który został już zaimportowany. Należy zauważyć, że ta procedura jest przykładem konfiguracji z jednym plikiem i jednym miejscem docelowym. Więcej informacji na temat zarządzania miejscami docelowymi raportowania elektronicznego można znaleźć na stronach Pomocy systemu Dynamics 365 Finance.

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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]