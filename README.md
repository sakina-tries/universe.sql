# universe.sql
--
-- PostgreSQL database dump
--

-- Dumped from database version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)
-- Dumped by pg_dump version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

DROP DATABASE universe;
--
-- Name: universe; Type: DATABASE; Schema: -; Owner: freecodecamp
--

CREATE DATABASE universe WITH TEMPLATE = template0 ENCODING = 'UTF8' LC_COLLATE = 'C.UTF-8' LC_CTYPE = 'C.UTF-8';


ALTER DATABASE universe OWNER TO freecodecamp;

\connect universe

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

SET default_tablespace = '';

SET default_table_access_method = heap;

--
-- Name: galaxy; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.galaxy (
    galaxy_id integer NOT NULL,
    name character varying NOT NULL,
    age integer,
    distance integer,
    life boolean,
    notes text,
    discovered_by text
);


ALTER TABLE public.galaxy OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_galaxy_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_galaxy_id_seq OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_galaxy_id_seq OWNED BY public.galaxy.galaxy_id;


--
-- Name: moon; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.moon (
    moon_id integer NOT NULL,
    name character varying NOT NULL,
    landed boolean,
    distance integer,
    planet_id integer,
    discovered_by text
);


ALTER TABLE public.moon OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_moon_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_moon_id_seq OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_moon_id_seq OWNED BY public.moon.moon_id;


--
-- Name: moreinfo; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.moreinfo (
    moreinfo_id integer NOT NULL,
    name character varying NOT NULL,
    date date,
    link text
);


ALTER TABLE public.moreinfo OWNER TO freecodecamp;

--
-- Name: moreinfo_moreinfo_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moreinfo_moreinfo_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moreinfo_moreinfo_id_seq OWNER TO freecodecamp;

--
-- Name: moreinfo_moreinfo_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moreinfo_moreinfo_id_seq OWNED BY public.moreinfo.moreinfo_id;


--
-- Name: planet; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.planet (
    planet_id integer NOT NULL,
    name character varying NOT NULL,
    age numeric,
    landed boolean,
    star_id integer,
    discovered_by text
);


ALTER TABLE public.planet OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_planet_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_planet_id_seq OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_planet_id_seq OWNED BY public.planet.planet_id;


--
-- Name: star; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.star (
    star_id integer NOT NULL,
    name character varying NOT NULL,
    age numeric,
    distance integer,
    galaxy_id integer,
    discovered_by text
);


ALTER TABLE public.star OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_star_id_seq OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_star_id_seq OWNED BY public.star.star_id;


--
-- Name: galaxy galaxy_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN galaxy_id SET DEFAULT nextval('public.galaxy_galaxy_id_seq'::regclass);


--
-- Name: moon moon_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN moon_id SET DEFAULT nextval('public.moon_moon_id_seq'::regclass);


--
-- Name: moreinfo moreinfo_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moreinfo ALTER COLUMN moreinfo_id SET DEFAULT nextval('public.moreinfo_moreinfo_id_seq'::regclass);


--
-- Name: planet planet_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN planet_id SET DEFAULT nextval('public.planet_planet_id_seq'::regclass);


--
-- Name: star star_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN star_id SET DEFAULT nextval('public.star_star_id_seq'::regclass);


--
-- Data for Name: galaxy; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.galaxy VALUES (1, 'milkyway', NULL, NULL, NULL, NULL, NULL);
INSERT INTO public.galaxy VALUES (2, 'andromeda', NULL, NULL, NULL, NULL, NULL);
INSERT INTO public.galaxy VALUES (3, 'anon1', NULL, NULL, NULL, NULL, NULL);
INSERT INTO public.galaxy VALUES (4, 'anon2', NULL, NULL, NULL, NULL, NULL);
INSERT INTO public.galaxy VALUES (5, 'anon3', NULL, NULL, NULL, NULL, NULL);
INSERT INTO public.galaxy VALUES (6, 'anon4', NULL, NULL, NULL, NULL, NULL);


--
-- Data for Name: moon; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.moon VALUES (1, 'callisto', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (2, 'oberon', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (3, 'elara', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (4, 'blue moon', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (5, 'atlas', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (6, 'triton', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (7, 'dione', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (8, 'helene', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (9, 'arche', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (10, 'hyperion', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (11, 'ariel', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (12, 'aitne', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (13, 'nikini', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (14, 'cressida', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (15, 'rosalind', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (16, 'namaka', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (17, 'full moon', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (18, 'luna', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (19, 'tungi', NULL, NULL, NULL, NULL);
INSERT INTO public.moon VALUES (20, 'bulan', NULL, NULL, NULL, NULL);


--
-- Data for Name: moreinfo; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.moreinfo VALUES (1, 'Sakina', NULL, NULL);
INSERT INTO public.moreinfo VALUES (2, 'fCC bot', NULL, NULL);
INSERT INTO public.moreinfo VALUES (3, 'anononymous', NULL, NULL);


--
-- Data for Name: planet; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.planet VALUES (1, 'Earth', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (2, 'Mars', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (3, 'Mercury', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (4, 'Saturn', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (5, 'Jupiter', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (6, 'Venus', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (7, 'Neptune', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (8, 'Uranus', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (9, 'Pluto', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (10, 'Igolla W8', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (11, 'Tulia', NULL, NULL, NULL, NULL);
INSERT INTO public.planet VALUES (12, 'Zexade', NULL, NULL, NULL, NULL);


--
-- Data for Name: star; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.star VALUES (1, 'orion', NULL, NULL, NULL, NULL);
INSERT INTO public.star VALUES (2, 'sirius', NULL, NULL, NULL, NULL);
INSERT INTO public.star VALUES (3, 'anon', NULL, NULL, NULL, NULL);
INSERT INTO public.star VALUES (4, 'anon2', NULL, NULL, NULL, NULL);
INSERT INTO public.star VALUES (5, 'anon3', NULL, NULL, NULL, NULL);
INSERT INTO public.star VALUES (6, 'anon4', NULL, NULL, NULL, NULL);


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_galaxy_id_seq', 6, true);


--
-- Name: moon_moon_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_moon_id_seq', 20, true);


--
-- Name: moreinfo_moreinfo_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moreinfo_moreinfo_id_seq', 3, true);


--
-- Name: planet_planet_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_planet_id_seq', 12, true);


--
-- Name: star_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_star_id_seq', 6, true);


--
-- Name: galaxy galaxy_discovered_by_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_discovered_by_key UNIQUE (discovered_by);


--
-- Name: galaxy galaxy_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_pkey PRIMARY KEY (galaxy_id);


--
-- Name: moon moon_discovered_by_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_discovered_by_key UNIQUE (discovered_by);


--
-- Name: moon moon_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_pkey PRIMARY KEY (moon_id);


--
-- Name: moreinfo moreinfo_link_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moreinfo
    ADD CONSTRAINT moreinfo_link_key UNIQUE (link);


--
-- Name: moreinfo moreinfo_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moreinfo
    ADD CONSTRAINT moreinfo_pkey PRIMARY KEY (moreinfo_id);


--
-- Name: planet planet_discovered_by_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_discovered_by_key UNIQUE (discovered_by);


--
-- Name: planet planet_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_pkey PRIMARY KEY (planet_id);


--
-- Name: star star_discovered_by_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_discovered_by_key UNIQUE (discovered_by);


--
-- Name: star star_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_pkey PRIMARY KEY (star_id);


--
-- Name: moon moon_planet_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_planet_fkey FOREIGN KEY (planet_id) REFERENCES public.planet(planet_id);


--
-- Name: planet planet_star_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_star_fkey FOREIGN KEY (star_id) REFERENCES public.star(star_id);


--
-- Name: star star_galaxy_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_galaxy_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);


--
-- PostgreSQL database dump complete
--

