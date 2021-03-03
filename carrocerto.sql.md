# -- phpMyAdmin SQL Dump
-- version 5.0.4
-- https://www.phpmyadmin.net/
--
-- Host: 127.0.0.1
-- Tempo de geração: 02-Mar-2021 às 17:40
-- Versão do servidor: 10.4.17-MariaDB
-- versão do PHP: 8.0.2

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Banco de dados: `carro_certo`
--

-- --------------------------------------------------------

--
-- Estrutura da tabela `adm`
--

CREATE TABLE `adm` (
  `id_adm` int(11) NOT NULL,
  `tipo` varchar(30) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- --------------------------------------------------------

--
-- Estrutura da tabela `automovel`
--

CREATE TABLE `automovel` (
  `marca` varchar(25) NOT NULL,
  `modelo` varchar(25) NOT NULL,
  `versao` varchar(30) NOT NULL,
  `ano` varchar(20) NOT NULL,
  `km` varchar(20) NOT NULL,
  `preco` varchar(20) NOT NULL,
  `Id_automovel` int(11) NOT NULL,
  `email_usuario` varchar(80) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Extraindo dados da tabela `automovel`
--

INSERT INTO `automovel` (`marca`, `modelo`, `versao`, `ano`, `km`, `preco`, `Id_automovel`, `email_usuario`) VALUES
('BMW', 'Renegade', 'Longitude', '2010', '3 KM', '12.000', 53, 'samuelaraujolse@gmail.com'),
('Audi', 'Compass', 'Longitude', '2011', '52', '30.000', 54, 'Ricksondbd@gmail.com'),
('BMW', 'Compass', 'Longitude', '2010', '2222 KM', '30.000', 55, 'samuelaraujolse@gmail.com'),
('Audi', 'Compass', 'Longitude', '2007', '2', '39000', 56, 'Ricksondbd@gmail.com'),
('Chevrolet', 'Renegade', 'Limited', '2008', '0', '60.000', 58, 'giovanni.android.ga@gmail.com'),
('Audi', 'Compass', 'Longitude', '2010', '0', '222', 60, 'samuelaraujolse@gmail.com'),
('Audi', 'Compass', 'Longitude', '2010', '22', '20.000', 61, 'samuelaraujolse@gmail.com');

-- --------------------------------------------------------

--
-- Estrutura da tabela `usuario`
--

CREATE TABLE `usuario` (
  `id` int(11) NOT NULL,
  `nome` varchar(50) NOT NULL,
  `cep` varchar(12) NOT NULL,
  `email` varchar(80) NOT NULL,
  `senha` varchar(30) NOT NULL,
  `cpf` varchar(22) NOT NULL,
  `endereco` varchar(30) NOT NULL,
  `telefone` varchar(30) NOT NULL,
  `cidade` varchar(30) NOT NULL,
  `estado` varchar(40) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Extraindo dados da tabela `usuario`
--

INSERT INTO `usuario` (`id`, `nome`, `cep`, `email`, `senha`, `cpf`, `endereco`, `telefone`, `cidade`, `estado`) VALUES
(1, 'Samuel Araujo Lopes', '73.340-501', 'samuelaraujolse@gmail.com', '91565104', '049.202.331-08', 'Quadra 5 Conjunto 5A', '(61) 9 9903-9629', 'Planaltina', 'Distrito Federal - (DF)'),
(3, 'Giovanni Anderson Rodrigues', '73.340-501', 'giovanni.android.ga@gmail.com', '91565104', '073.463.961-97', 'Quadra 5 Conjunto 5A', '(61) 9 8531-2268', 'Brasilia', 'Distrito Federal - (DF)'),
(5, 'Rickson Queiroz', '73.340-501', 'Ricksondbd@gmail.com', '91565104', '123.131.231-23', 'Quadra 5 Conjunto 5A 38', '(61) 9 9999-999', 'Brasilia', 'Distrito Federal - (DF)'),
(6, 'Rickson Queiroz', '73.340-501', 'Ricksondbd@gmail.com1', '91565104', '073.463.961-97', 'Quadra 5 Conjunto 5A 38', '(61) 9 9999-999', 'Brasilia', 'Rio de Janeiro - (RJ)'),
(9, 'Samuel Araujo Lopes', '73.340-501', 'samuelaraujolse1@gmail.com', '91565104', '049.202.331-08', 'Quadra 5 Conjunto 5A 38', '(55) 6 1999-0396', 'Planaltina', 'Rio de Janeiro - (RJ)'),
(10, 'Samuel Araujo Lopes', '73.340-501', 'samuelaraujolse1@gmail.com', '91565104', '049.202.331-08', 'Quadra 5 Conjunto 5A 38', '(55) 6 1999-0396', 'Planaltina', 'Piaui­ - (PI)');

-- --------------------------------------------------------

--
-- Estrutura da tabela `vendas`
--

CREATE TABLE `vendas` (
  `id_venda` int(11) NOT NULL,
  `nome` varchar(30) NOT NULL,
  `data` varchar(30) NOT NULL,
  `pagamento` varchar(30) NOT NULL,
  `valor` varchar(25) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- --------------------------------------------------------

--
-- Estrutura da tabela `venda_solicitacao`
--

CREATE TABLE `venda_solicitacao` (
  `nome` varchar(30) NOT NULL,
  `cpf` varchar(30) NOT NULL,
  `email` varchar(80) NOT NULL,
  `telefone` varchar(80) NOT NULL,
  `cep` varchar(20) NOT NULL,
  `endereco` varchar(50) NOT NULL,
  `estado` varchar(50) NOT NULL,
  `cidade` varchar(40) NOT NULL,
  `banco` varchar(30) NOT NULL,
  `entrada` varchar(50) NOT NULL,
  `parcelas` varchar(30) NOT NULL,
  `id_solicitacao` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Extraindo dados da tabela `venda_solicitacao`
--

INSERT INTO `venda_solicitacao` (`nome`, `cpf`, `email`, `telefone`, `cep`, `endereco`, `estado`, `cidade`, `banco`, `entrada`, `parcelas`, `id_solicitacao`) VALUES
('Rickson Queiroz', '049.202.331-08', 'Rickson.Queirozz@gmail.com', '(61) 9 9999-999', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'Rio de Janeiro - (RJ)', 'Brasilia', 'Itaú', '500', '12X', 6),
('Samuel Araujo Lopes', '049.202.331-08', 'samuelaraujolse@gmail.com', '(55) 6 1999-0396', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'UF', 'Planaltina', 'Itaú', '500', '12X', 7),
('Samuel Araujo Lopes', '049.202.331-08', 'samuelaraujolse@gmail.com', '(55) 6 1999-0396', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'UF', 'Planaltina', 'Itaú', '500', '24X', 8),
('Samuel Araujo Lopes', '049.202.331-08', 'samuelaraujolse@gmail.com', '(55) 6 1999-0396', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'UF', 'Planaltina', 'Itaú', '500', '36X', 9),
('Samuel Araujo Lopes', '049.202.331-08', 'samuelaraujolse11@gmail.com', '(55) 6 1999-0396', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'Distrito Federal - (DF)', 'Planaltina', 'Itaú', '500', '12X', 10),
('Samuel Araujo Lopes', '049.202.331-08', 'samuelaraujolse@gmail.com', '(55) 6 1999-0396', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'Distrito Federal - (DF)', 'Planaltina', 'Itaú', '500', '12X', 11),
('Samuel Araujo Lopes', '049.202.331-09', 'samuelaraujolse@gmail.com', '(55) 6 1999-0396', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'UF', 'Planaltina', 'Itaú', '500', '36X', 12),
('Jeferson Lopes', '000.000.00', 'jhefinho682@gmail.com', '(61) 9 9999-99', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'Distrito Federal - (DF)', 'Planaltina', 'Alpha', '500', '48X', 13),
('Samuel Araujo Lopes', '049.202.331-08', 'samuelaraujolse@gmail.com', '(55) 6 1999-0396', '73.340-501', 'Quadra 5 Conjunto 5A 38', 'UF', 'Planaltina', 'Alpha', '500', '36X', 14);

-- --------------------------------------------------------

--
-- Estrutura da tabela `verifica_login`
--

CREATE TABLE `verifica_login` (
  `id_login` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Índices para tabelas despejadas
--

--
-- Índices para tabela `adm`
--
ALTER TABLE `adm`
  ADD PRIMARY KEY (`id_adm`);

--
-- Índices para tabela `automovel`
--
ALTER TABLE `automovel`
  ADD PRIMARY KEY (`Id_automovel`);

--
-- Índices para tabela `usuario`
--
ALTER TABLE `usuario`
  ADD PRIMARY KEY (`id`);

--
-- Índices para tabela `vendas`
--
ALTER TABLE `vendas`
  ADD PRIMARY KEY (`id_venda`);

--
-- Índices para tabela `venda_solicitacao`
--
ALTER TABLE `venda_solicitacao`
  ADD PRIMARY KEY (`id_solicitacao`);

--
-- AUTO_INCREMENT de tabelas despejadas
--

--
-- AUTO_INCREMENT de tabela `adm`
--
ALTER TABLE `adm`
  MODIFY `id_adm` int(11) NOT NULL AUTO_INCREMENT;

--
-- AUTO_INCREMENT de tabela `automovel`
--
ALTER TABLE `automovel`
  MODIFY `Id_automovel` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=62;

--
-- AUTO_INCREMENT de tabela `usuario`
--
ALTER TABLE `usuario`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=11;

--
-- AUTO_INCREMENT de tabela `vendas`
--
ALTER TABLE `vendas`
  MODIFY `id_venda` int(11) NOT NULL AUTO_INCREMENT;

--
-- AUTO_INCREMENT de tabela `venda_solicitacao`
--
ALTER TABLE `venda_solicitacao`
  MODIFY `id_solicitacao` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=15;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
