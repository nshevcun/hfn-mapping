<html lang="en">
<head>
    <meta charset="utf-8">

    <title>Hollywood Fight Nights - Seat Map</title>
    <meta name="description" content="Hollywood Fight Nights - Interactive Seat Map Stadium">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- STYLES AND SCRIPTS -->
    <!-- GSAP -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/1.20.3/TweenMax.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/1.20.3/utils/Draggable.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/material-design-lite/1.3.0/material.min.js"></script>

    <!-- jQuery -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js" integrity="sha512-894YE6QWD5I59HgZOGReFYm4dnWc1Qt5NtvYSaNcOP+u1T9qYdvdihz0PPSiiqn/+/3e7Jo4EaG7TubfWGUrMQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>

    <script>
    // HIDING THE LOADER
    $(document).ready(function() {
        setTimeout(function(){
            $(".ui-loader").hide();
        },10);
    });
    </script>

    <!-- jQuery for Mobile -->
    <script src="https://code.jquery.com/mobile/1.5.0-alpha.1/jquery.mobile-1.5.0-alpha.1.min.js" integrity="sha256-rmrOpoF72PrJyKdBjU7EflkHQLk2yLVBEe7WN4TJ0nc=" crossorigin="anonymous"></script>

    <!-- Hammer JS -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/hammer.js/2.0.8/hammer.min.js" integrity="sha512-UXumZrZNiOwnTcZSHLOfcTs0aos2MzBWHXOHOuB0J/R44QB0dwY5JgfbvljXcklVf65Gc4El6RjZ+lnwd2az2g==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>

    <!-- Font-Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" integrity="sha512-iBBXm8fW90+nuLcSKlbmrPcLa0OT92xO1BIsZ+ywDWZCvqsWgccV3gFoRBv0z+8dLJgyAHIhR35VZc2oM/gI1w==" crossorigin="anonymous" referrerpolicy="no-referrer" />

    <style>
        .container {
            height: 600px;
            width: 90%;
            overflow-x: hidden;
            overflow-y: hidden;
            position: relative;
            border: solid 1px #006fbd;
            display: block;
            margin-left: auto;
            margin-right: auto;
            margin-top: 30px;
        }

        .textcenter {
            text-align: center;
        }

        .svg {
            position: relative;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            cursor: move;
        }

        .svg-scrim {
            pointer-events: none;
            z-index: 5;
        }

        .proxy {
            fill: none;
            stroke: none;
        }

        .controls {
            position: relative;
            top: 0;
            left: 0;
            padding: 12px;
            z-index: 10;
            display: block;
            margin-left: auto;
            margin-right: auto;
            text-align: center;
        }

        .controls-button {
            font-weight: 700;
        }

        .zoom-buttons {
            position: absolute;
            top: 10px;
            left: 5px;
            margin: 10px;
            z-index: 11;
        }

        .zoom-buttons .fa {
            color: #006fbd;
            margin: 5px;
        }

        #zoomIn, #zoomOut {
            cursor: pointer;
        }

        .info {
            user-select: none;
            pointer-events: none;
        }

        ul {
            font-size: 13px;
            list-style-type: none;
            padding: 0;
            line-height: 20px;
            margin-top: 0;
        }

        .svg-background {
            fill: none;
            stroke: none;
        }

        .green {
            fill: green !important;
        }

        .grey {
            fill: grey !important;
        }

        .yellow {
            fill: yellow !important;
        }

        .booth-fill-grey {
            fill: #ccc;
        }

        .booth > text {
            pointer-events: none;
        }

    	.cross-line {
    		stroke: white;
    	}

    	.cross-line-grey {
    		stroke: #ccc;
    	}

    	.cross-line-green {
    		stroke: green;
    	}

    	.cross-line-yellow {
    		stroke: yellow;
    	}

    </style>

</head>

<body>

    <!-- The Selected Booth Display and Zoom Buttons -->

    <div class="textcenter">
        <b><p>Selected Seats: <span id="booth-cart"></span></p></b>
    </div>


    <div class="container" id="container">

    	<div class="zoom-buttons">
    		<div id="zoomIn">
    			<i class="fa fa-plus-circle fa-2x"></i>
    		</div>

    		<div id="zoomOut">
    			<i class="fa fa-minus-circle fa-2x"></i>
    		</div>
    	</div>

    	<!-- The main SVG container -->

    	<svg version="1.1" id="svg" class="svg" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
    		x="0px" y="0px" width="5000px" height="7000px" viewBox="0 0 5000 7000" enable-background="new 0 0 5000 7000"
    		xml:space="preserve">
    		<g id="viewport">
    			<rect id="stadium" x="1742" y="2607" fill="#D1D3D4" stroke="#000000" stroke-width="2" stroke-miterlimit="10"
    				width="1501.891" height="1479" />
    			<rect id="background" x="205" y="469" fill="none" stroke="#000000" stroke-width="10" stroke-miterlimit="10"
    				width="4488" height="5880" />

    			<!-- SECTION A -->

    			<!-- A ROW 1 -->

    			<g id="seat-2335" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1816.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2335" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1771.1,2432.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1803.4,2432.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2336" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1874.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2336" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1829.1,2432.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1861.4,2433.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2337" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1932.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2337" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1887.1,2432.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1919.4,2433.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2338" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1990.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2338" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1945.1,2433.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1977.4,2433.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2339" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2048.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2339" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2003.1,2432.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2035.4,2432.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2340" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2106.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2340" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2061.1,2430.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2093.4,2430.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2341" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2164.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2341" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2119.1,2430.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2151.4,2430.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2342" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2222.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2342" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2177.1,2430.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2209.4,2430.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2343" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2280.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2343" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2235.1,2430.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2267.4,2430.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2344" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2338.5,2467.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2467.693z" />
    				<g id="cross-2344" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2293.1,2433.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2325.4,2433.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 2 -->

    			<g id="seat-2345" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2668.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2345" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2623.1,2430.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655.4,2431.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2346" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2727.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2346" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2682.1,2430c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2714.4,2430.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2347" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2786.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2347" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2741.1,2430.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2773.4,2431.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2348" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2845.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2348" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2799.9,2431.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2832.2,2431.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2349" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2904.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2349" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2859.1,2429.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891.4,2429.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2350" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2963.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2350" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2918.1,2429.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2950.4,2430.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2351" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3022.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2351" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2977.1,2429.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009.4,2429.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2352" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3081.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2352" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3036.1,2430c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3068.4,2430.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2353" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3140.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2353" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3095.1,2429.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3127.4,2429.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2354" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3199.5,2465.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2465.693z" />
    				<g id="cross-2354" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3154.1,2430.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3186.4,2430.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 3 -->

    			<g id="seat-2355" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1700.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2355" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1655.1,2314.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1687.4,2314.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2356" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1758.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2356" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1713.1,2314.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1745.4,2315.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2357" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1816.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2357" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1770.9,2314.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1803.2,2314.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2358" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1874.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2358" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1829.3,2314.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1861.6,2314.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2359" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1932.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2359" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1886.9,2314.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1919.2,2315.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2360" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1990.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2360" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1944.9,2314.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1977.2,2314.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2361" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2048.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2361">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2003.3,2314c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2035.6,2314.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2362" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2106.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2362" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2060.9,2313.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2093.2,2314.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2363" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2164.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2363">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2118.9,2315.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2151.2,2315.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2364" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2222.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2364" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2176.9,2314.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2209.2,2315c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2365" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2280.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2365" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2234.9,2315.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2267.2,2315.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2366" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2338.5,2351.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2366" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2293.3,2315.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2325.6,2315.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 4 -->

    			<g id="seat-2367" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2668.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2367" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2622.9,2314.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655.2,2315.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2368" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2727.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2368" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2681.9,2315.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2714.2,2315.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2369" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2786.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2369" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2740.9,2315.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2773.2,2315.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2370" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2845.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2370" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2799.7,2315.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2832,2315.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2371" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2904.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2371" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2858.9,2314.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891.2,2314.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2372" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2963.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2372" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2918.3,2315.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2950.6,2316.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2373" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3022.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2373" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2977.3,2314.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009.6,2314.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2374" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3081.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2374" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3036.5,2314.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3068.8,2315.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2375" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3140.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2375" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3095.3,2315.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3127.6,2316.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2376" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3199.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2376" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3154.3,2316.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3186.6,2316.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2377" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3258.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2377" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3213.3,2316.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3245.6,2316.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2378" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3317.5,2351.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2351.693z" />
    				<g id="cross-2378" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3272.1,2316.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3304.4,2316.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 5 -->

    			<g id="seat-2379" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1583.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2379" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1538.1,2206.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1570.4,2206.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2380" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1641.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2380" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1596.1,2206.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1628.4,2207.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2381" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1700.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2381" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1654.9,2206.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1687.2,2207.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2382" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1758.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2382" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1712.9,2207.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1745.2,2207.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2383" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1816.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2383" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1771.3,2207.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1803.6,2207.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2384" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1874.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2384" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1828.9,2207.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1861.2,2207.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2385" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1932.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2385" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1886.7,2207.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1919,2207.7c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2386" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1990.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2386" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1944.7,2207.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1977,2208.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2387" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2048.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2387" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2002.9,2207.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2035.2,2208.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2388" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2106.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2388" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2060.7,2208.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2093,2208.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2389" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2164.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2389" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2118.7,2208.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2151,2208.7c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2390" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2222.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2390" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2176.7,2208.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2209,2208.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2391" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2280.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2391" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2234.7,2208.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2267,2208.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2392" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2338.5,2243.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2243.693z" />
    				<g id="cross-2392" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2292.9,2208.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2325.2,2208.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 6 -->

    			<g id="seat-2393" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2668.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2393" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2622.7,2206.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655,2206.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2394" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2727.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2394" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2682.1,2206.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2714.4,2207.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2395" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2786.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2395" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2740.7,2208.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2773,2208.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2396" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2845.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2396" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2800.1,2206.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2832.4,2207.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2397" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2904.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2397" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2858.7,2208.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891,2208.6c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2398" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2963.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2398" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2918.5,2208.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2950.8,2208.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2399" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3022.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2399" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2977.1,2208.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009.4,2208.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2400" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3081.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2400" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3035.9,2208.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3068.2,2208.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2401" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3140.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2401" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3095.5,2208.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3127.8,2209c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2402" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3199.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2402" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3154.5,2208.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3186.8,2208.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2403" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3258.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2403" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3213.5,2208.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3245.8,2209.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2404" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3317.5,2242.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2242.693z" />
    				<g id="cross-2404" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3272.3,2209c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3304.6,2209.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 7 -->

    			<g id="seat-2405" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1583.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2405" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1537.9,2085.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1570.2,2085.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2406" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1641.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2406" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1596.3,2085.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1628.6,2085.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2407" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1700.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2407" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1654.7,2085.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1687,2086.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2408" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1758.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2408" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1712.7,2085.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1745,2086.3c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2409" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1816.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2409" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1770.7,2085.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1803,2085.5c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2410" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1874.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2410" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1828.7,2086c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1861,2086.3c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2411" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1932.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2411" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1886.5,2085.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1918.8,2086.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2412" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1990.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2412" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1944.5,2085.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1976.8,2086c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2413" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2048.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2413" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2002.9,2086.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2035.2,2086.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2414" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2106.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2414" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2060.5,2086c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2092.8,2086.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2415" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2164.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2415" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2119.3,2086.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2151.6,2086.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2416" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2222.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2416" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2176.5,2086c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2208.8,2086.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2417" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2280.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2417" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2234.5,2086c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2266.8,2086.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2418" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2338.5,2122.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2418" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2292.7,2086c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2325,2086.3c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>

    			<!-- A ROW 8 -->

    			<g id="seat-2419" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2668.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2419" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2622.7,2086.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655,2086.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2420" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2727.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2420" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2681.7,2086.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2714,2087.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2421" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2786.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2421" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2740.5,2086.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.8,2087.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2422" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2845.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2422" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2799.5,2087.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.8,2087.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2423" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2904.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2423" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2859.3,2087.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891.6,2087.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2424" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2963.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2424" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2918.3,2087.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2950.6,2088c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2425" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3022.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2425" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2976.9,2087.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009.2,2087.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2426" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3081.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2426" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3036.3,2086.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3068.6,2086.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2427" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3140.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2427" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3095.7,2085.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3128,2085.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2428" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3199.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2428" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3154.7,2086.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3187,2086.7c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2429" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3258.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2429" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3213.7,2087.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3246,2088.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2430" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3317.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2430" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3271.9,2087.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3304.2,2087.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2431" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3376.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2431" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3331.1,2087.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3363.4,2087.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2432" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3435.5,2122.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2122.693z" />
    				<g id="cross-2432" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3390.1,2087.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3422.4,2087.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 9 -->

    			<g id="seat-2433" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1583.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2433" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1537.7,1977.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1570,1977.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2434" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1641.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2434" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1596.5,1977.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1628.8,1978.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2435" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1700.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2435" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1654.5,1977.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1686.8,1978.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2436" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1758.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2436" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1712.5,1978.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1744.8,1978.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2437" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1816.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2437" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1770.5,1978.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1802.8,1978.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2438" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1874.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2438" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1828.5,1978.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1860.8,1978.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2439" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1932.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2439" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1886.3,1978.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1918.6,1979.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2440" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1990.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2440" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1944.3,1978.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1976.6,1979.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2441" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2048.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2441" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2002.7,1979.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2035,1979.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2442" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2106.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2442" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2060.3,1979.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2092.6,1979.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2443" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2164.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2443" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2118.5,1979.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2150.8,1979.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2444" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2222.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2444" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2176.7,1979.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2209,1979.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2445" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2280.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2445" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2234.1,1979.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2266.4,1979.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2446" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2338.5,2014.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2014.693z" />
    				<g id="cross-2446" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2292.5,1979.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2324.8,1979.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 10 -->

    			<g id="seat-2447" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2668.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2447" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2622.9,1977.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655.2,1978c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2448" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2727.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2448" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2681.5,1978.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2713.8,1979c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2449" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2786.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2449" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2740.3,1977.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.6,1978.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2450" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2845.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2450" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2799.3,1978.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.6,1978.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2451" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2904.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2451" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2859.5,1977.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891.8,1978.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2452" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2963.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2452" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2918.1,1978c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2950.4,1978.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2453" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3022.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2453" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2976.7,1978c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009,1978.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2454" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3081.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2454" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3036.5,1978.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3068.8,1978.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2455" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3140.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2455" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3095.9,1977.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3128.2,1978.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2456" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3199.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2456" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3154.1,1977.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3186.4,1977.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2457" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3258.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2457" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3213.9,1978c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3246.2,1978.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2458" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3317.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2458" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3271.7,1978.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3304,1979.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2459" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3376.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2459" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3331.3,1979c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3363.6,1979.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2460" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3435.5,2013.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V2013.693z" />
    				<g id="cross-2460" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3390.3,1978c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3422.6,1978.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 11 -->

    			<g id="seat-2461" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1455.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2461" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1409.1,1860.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1441.4,1861.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2462" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1514.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2462" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1468.1,1861.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1500.4,1861.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2463" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1573.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2463" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1526.1,1861.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1558.4,1861.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2464" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1632.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2464" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1587.1,1861.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1619.4,1861.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2465" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1690.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2465" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1645.1,1861.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1677.4,1862.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2466" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1749.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2466" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1704.1,1861.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1736.4,1862.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2467" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1807.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2467" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1763.1,1862.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1795.4,1862.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2468" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1866.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2468" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1821.1,1862.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1853.4,1862.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2469" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1925.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2469" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1880.1,1862.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1912.4,1862.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2470" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1984.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2470" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1939.1,1862.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1971.4,1863c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2471" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2043.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2471" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1998.1,1862.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2030.4,1863.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2472" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2102.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2472" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2057.1,1863c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2089.4,1863.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2473" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2161.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2473" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2116.1,1863.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2148.4,1863.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2474" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2220.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2474" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2175.1,1863.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2207.4,1863.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2475" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2279.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2475" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2233.9,1862.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2266.2,1862.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2476" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2338.5,1897.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1897.693z" />
    				<g id="cross-2476" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2292.3,1860.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2324.6,1860.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 12 -->

    			<g id="seat-2477" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2668.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2477" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2623.1,1860.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655.4,1860.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2478" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2727.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2478" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2681.3,1860.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2713.6,1861.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2479" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2786.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2479" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2741.1,1861.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2773.4,1861.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2480" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2845.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2480" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2799.1,1860.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.4,1860.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2481" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2904.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2481" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2859.3,1860.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891.6,1860.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2482" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2963.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2482" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2917.9,1860.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2950.2,1860.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2483" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3022.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2483" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2976.5,1860.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3008.8,1861.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2484" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3081.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2484" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3036.7,1860.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3069,1860.5c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2485" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3140.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2485" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3095.1,1861.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3127.4,1862.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2486" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3199.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2486" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3153.9,1861.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3186.2,1862.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2487" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3258.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2487" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3214.1,1860.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3246.4,1860.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2488" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3317.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2488" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3271.9,1862.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3304.2,1862.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2489" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3376.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2489" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3331.5,1860.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3363.8,1860.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2490" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3435.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2490" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3390.5,1860.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3422.8,1860.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2491" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3494.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2491" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3449.1,1859.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3481.4,1859.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2492" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3553.5,1895.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1895.693z" />
    				<g id="cross-2492" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3508.1,1859.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3540.4,1859.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 13 -->

    			<g id="seat-2493" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1336.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2493" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1291.1,1756.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1323.4,1756.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2494" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1395.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2494" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1350.1,1756.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1382.4,1756.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2495" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1454.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2495" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1410.1,1756.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1442.4,1756.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2496" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1513.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2496" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1467.9,1756c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1500.2,1756.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2497" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1571.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2497" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1526.3,1756.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1558.6,1757.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2498" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1630.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2498" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1585.3,1756.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1617.6,1757.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2499" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1689.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2499" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1644.3,1756.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1676.6,1757.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2500" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1748.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2500" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1703.1,1757.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1735.4,1757.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2501" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1807.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2501" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1762.1,1756.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1794.4,1756.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2502" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1866.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2502" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1820.9,1757.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1853.2,1757.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2503" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1925.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2503" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1879.9,1757.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1912.2,1757.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2504" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1984.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2504" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1939.1,1757.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1971.4,1758.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2505" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2043.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2505" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1997.9,1757.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2030.2,1758.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2506" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2102.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2506" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2056.9,1758.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2089.2,1758.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2507" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2161.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2507" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2115.9,1758.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2148.2,1758.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2508" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2220.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2508" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2175.3,1757.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2207.6,1758.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2509" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2279.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2509" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2235.1,1758.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2267.4,1758.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2510" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2338.5,1793.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1793.693z" />
    				<g id="cross-2510" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2292.1,1756.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2324.4,1756.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 14 -->

    			<g id="seat-2511" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2668.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2511" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2623.3,1751.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655.6,1751.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2512" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2727.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2512" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2681.1,1751.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2713.4,1752.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2513" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2786.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2513" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2740.9,1752.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2773.2,1752.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2514" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2845.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2514" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2798.9,1752.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.3,1752.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2515" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2904.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2515" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2859.1,1752.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891.4,1752.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2516" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2963.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2516" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2917.7,1752.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2950,1753.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2517" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3022.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2517" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2977.1,1752.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009.4,1753.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2518" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3081.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2518" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3036.9,1753.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3069.2,1753.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2519" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3140.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2519" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3094.9,1753.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3127.2,1753.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2520" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3199.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2520" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3153.7,1753.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3186,1753.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2521" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3258.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2521" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3214.2,1753.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3246.6,1753.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2522" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3317.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2522" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3272.1,1753.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3304.4,1753.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2523" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3376.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2523" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3331.7,1753.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3364,1754c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2524" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3435.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2524" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3390.7,1753.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3423,1754.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2525" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3494.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2525" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3449.3,1754c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3481.6,1754.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2526" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3553.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2526" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3508.3,1754.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3540.6,1754.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2527" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3612.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2527" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567.1,1754.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3599.4,1754.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2528" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3670.5,1788.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1788.693z" />
    				<g id="cross-2528" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3625.1,1754.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3657.4,1755c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>

    			<!-- A ROW 15 -->

    			<g id="seat-2529" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1218.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2529" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1173.5,1640.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1205.8,1641.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2530" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1277.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2530" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1232.1,1641.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1264.4,1641.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2531" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1336.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2531" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1290.9,1641.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1323.2,1641.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2532" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1395.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2532" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1349.9,1641.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1382.2,1641.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2533" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1454.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2533" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1410.3,1641.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1442.6,1642.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2534" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1513.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2534" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1467.7,1641.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1500,1642.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2535" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1572.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2535" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1528.1,1642.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1560.4,1642.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2536" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1631.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2536" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1585.1,1642.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1617.4,1642.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2537" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1690.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2537" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1644.1,1642.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1676.4,1642.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2538" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1749.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2538" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1702.9,1642.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1735.2,1643c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2539" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1808.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2539" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1761.9,1642.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1794.2,1643.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2540" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1867.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2540" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1822.1,1643c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1854.4,1643.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2541" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1926.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2541" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1881.1,1643.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1913.4,1643.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2542" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1985.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2542" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1940.1,1643.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1972.4,1643.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2543" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2044.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2543" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1997.7,1643.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2030,1644c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2544" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2103.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2544" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2058.1,1643.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2090.4,1644.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2545" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2162.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2545" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2116.7,1643c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2149,1643.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2546" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2220.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2546" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2175.5,1642.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2207.8,1642.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2547" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2279.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2547" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2235.3,1642c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2267.6,1642.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2548" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2338.5,1677.693
    				c0,1.78,0.089,4.566-1.147,5.733c-1.236,1.167-3.796,0.713-5.682,0.713h-44.842c-1.885,0-4.282,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.374-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2548" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2292.3,1641.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2324.6,1641.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- A ROW 16 -->

    			<g id="seat-2549" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2668.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2549" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2623.5,1642.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655.8,1642.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2550" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2727.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2550" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2682.1,1642c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2714.4,1642.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2551" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2786.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2551" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2740.5,1642c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.8,1642.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2552" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2845.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2552" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2798.8,1642c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.1,1642.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2553" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2904.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2553" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2858.9,1642c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891.2,1642.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2554" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2963.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2554" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2917.5,1642.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.8,1642.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2555" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3022.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2555" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2977.3,1642.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009.6,1642.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2556" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3081.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2556" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3037.1,1642.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3069.4,1643.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2557" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3140.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2557" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3094.7,1642.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3127,1643.3c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2558" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3199.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2558" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3153.5,1643.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3185.8,1643.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2559" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3258.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2559" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3213.1,1643.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3245.4,1643.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2560" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3317.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2560" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3272.3,1643.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3304.6,1643.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2561" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3376.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2561" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3331.9,1643.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3364.2,1644.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2562" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3435.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2562" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3390.9,1642.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3423.2,1643.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2563" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3494.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2563" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3449.5,1643.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3481.8,1643.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2564" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3553.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2564" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3508.5,1642.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3540.8,1642.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2565" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3612.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2565" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3566.9,1642.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3599.2,1642.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2566" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3670.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2566" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3624.9,1642.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3657.2,1643c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2567" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3729.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2567" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3684.1,1642.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3716.4,1642.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2568" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3788.5,1677.693
    				c0,1.78,0.089,4.566-1.146,5.733c-1.236,1.167-3.797,0.713-5.683,0.713h-44.843c-1.885,0-4.281,0.452-5.517-0.713
    				c-1.237-1.167-1.312-3.953-1.312-5.733v-34.38c6.373-15.686,25.593-14.143,29.365-14.143l0,0c3.771,0,25.038-0.102,29.135,13.712
    				V1677.693z" />
    				<g id="cross-2568" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3743.1,1642.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3775.4,1643.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- SECTION B -->

    			<!-- B ROW 1 -->

    			<g id="seat-2569" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,2699.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,2699.248z" />
    				<g id="cross-2569" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3418.5,2653.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3450.8,2654.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2570" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,2757.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,2757.248z" />
    				<g id="cross-2570" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3418.3,2711.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3450.6,2712.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2571" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,2815.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,2815.248z" />
    				<g id="cross-2571" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3418.3,2769.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3450.6,2770.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2572" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,2873.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,2873.248z" />
    				<g id="cross-2572" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3418.3,2827.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3450.6,2828.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2573" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,2931.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,2931.248z" />
    				<g id="cross-2573" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3418.1,2885.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3450.4,2886.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2574" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,2989.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,2989.248z" />
    				<g id="cross-2574" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3418.7,2943.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3451,2944.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2575" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,3047.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,3047.248z" />
    				<g id="cross-2575" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3417.9,3001.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3450.2,3002.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2576" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,3106.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,3106.248z" />
    				<g id="cross-2576" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3417.7,3060.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3450,3061.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2577" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,3165.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,3165.248z" />
    				<g id="cross-2577" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3417.5,3119.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3449.8,3120.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2578" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3413.876,3224.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3413.876,3224.248z" />
    				<g id="cross-2578" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3417.7,3178.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3450,3179.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>

    			<!-- B ROW 2 -->

    			<g id="seat-2579" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,3552.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,3552.248z" />
    				<g id="cross-2579" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3417.3,3506.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3449.6,3507.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2580" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,3610.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,3610.248z" />
    				<g id="cross-2580" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3417.2,3564.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3449.5,3565.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2581" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,3669.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,3669.248z" />
    				<g id="cross-2581" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3417,3623.8c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3449.3,3624.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2582" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,3727.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,3727.248z" />
    				<g id="cross-2582" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3416.8,3681.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3449.1,3682.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2583" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,3785.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,3785.248z" />
    				<g id="cross-2583" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3416.6,3739.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3448.9,3740.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2584" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,3843.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,3843.248z" />
    				<g id="cross-2584" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3416.4,3797.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3448.7,3798.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2585" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,3901.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,3901.248z" />
    				<g id="cross-2585" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3416.6,3855.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3448.9,3856.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2586" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,3960.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,3960.248z" />
    				<g id="cross-2586" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3416.2,3914.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3448.5,3915.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2587" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,4019.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,4019.248z" />
    				<g id="cross-2587" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3416.6,3973.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3448.9,3974.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2588" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3414.876,4078.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3414.876,4078.248z" />
    				<g id="cross-2588" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3416,4032.8c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3448.3,4033.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 3 -->

    			<g id="seat-2589" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,2699.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,2699.248z" />
    				<g id="cross-2589" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.5,2653.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567.8,2653.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2590" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,2757.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,2757.248z" />
    				<g id="cross-2590" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.7,2711.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3568,2711.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2591" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,2815.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,2815.248z" />
    				<g id="cross-2591" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.3,2769.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567.6,2769.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2592" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,2873.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,2873.248z" />
    				<g id="cross-2592" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.3,2827.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567.6,2828.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2593" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,2931.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,2931.248z" />
    				<g id="cross-2593" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.9,2885.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3568.2,2886.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2594" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,2989.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,2989.248z" />
    				<g id="cross-2594" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.3,2943.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567.6,2943.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2595" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3047.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,3047.248z" />
    				<g id="cross-2595" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.1,3001.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567.4,3001.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2596" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3106.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,3106.248z" />
    				<g id="cross-2596" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3534.9,3060.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567.2,3061.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2597" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3165.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,3165.248z" />
    				<g id="cross-2597" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3534.7,3119.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567,3119.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2598" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3224.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3530.876,3224.248z" />
    				<g id="cross-2598" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3534.5,3178.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3566.8,3178.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 4 -->

    			<g id="seat-2599" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3552.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,3552.248z" />
    				<g id="cross-2599" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3534.3,3506.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3566.6,3506.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2600" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3610.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,3610.248z" />
    				<g id="cross-2600" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3534.2,3564.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3566.5,3564.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2601" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3669.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,3669.248z" />
    				<g id="cross-2601" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3534.3,3623.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3566.6,3623.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2602" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3727.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,3727.248z" />
    				<g id="cross-2602" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3534,3681.6c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3566.3,3681.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2603" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3785.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,3785.248z" />
    				<g id="cross-2603" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3533.8,3739.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3566.1,3740.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2604" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3843.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,3843.248z" />
    				<g id="cross-2604" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3533.6,3797.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3565.9,3798.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2605" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3901.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,3901.248z" />
    				<g id="cross-2605" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.5,3855.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3567.8,3856.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2606" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,3960.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,3960.248z" />
    				<g id="cross-2606" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.7,3914.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3568,3914.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2607" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,4019.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,4019.248z" />
    				<g id="cross-2607" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3535.9,3973.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3568.2,3974.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2608" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3530.876,4078.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3530.876,4078.248z" />
    				<g id="cross-2608" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3536.1,4032.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3568.4,4033.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 5 -->

    			<g id="seat-2609" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,2699.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,2699.248z" />
    				<g id="cross-2609" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3643.5,2653.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3675.8,2653.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2610" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,2757.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,2757.248z" />
    				<g id="cross-2610" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3643.3,2711.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3675.6,2711.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2611" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,2815.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,2815.248z" />
    				<g id="cross-2611" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3643.7,2769.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3676,2769.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2612" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,2873.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,2873.248z" />
    				<g id="cross-2612" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3643.9,2827.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3676.2,2827.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2613" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,2931.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,2931.248z" />
    				<g id="cross-2613" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3644.1,2886.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3676.4,2886.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2614" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,2989.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,2989.248z" />
    				<g id="cross-2614" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3643.1,2943.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3675.4,2943.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2615" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,3047.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,3047.248z" />
    				<g id="cross-2615" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3642.9,3001.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3675.2,3001.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2616" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,3106.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,3106.248z" />
    				<g id="cross-2616" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3642.5,3061.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3674.8,3061.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2617" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,3165.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,3165.248z" />
    				<g id="cross-2617" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3642.3,3119.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3674.6,3119.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2618" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3638.876,3224.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3638.876,3224.248z" />
    				<g id="cross-2618" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3642.2,3178.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3674.5,3178.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 6 -->

    			<g id="seat-2619" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,3552.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,3552.248z" />
    				<g id="cross-2619" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3647.5,3506.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3679.8,3506.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2620" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,3610.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,3610.248z" />
    				<g id="cross-2620" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3647.7,3564.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3680,3564.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2621" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,3669.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,3669.248z" />
    				<g id="cross-2621" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3647.3,3623.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3679.6,3623.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2622" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,3727.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,3727.248z" />
    				<g id="cross-2622" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3647.1,3681.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3679.4,3681.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2623" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,3785.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,3785.248z" />
    				<g id="cross-2623" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3647.7,3740.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3680,3740.5c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2624" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,3843.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,3843.248z" />
    				<g id="cross-2624" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3646.9,3798.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3679.2,3798.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2625" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,3901.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,3901.248z" />
    				<g id="cross-2625" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3647.9,3856.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3680.2,3856.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2626" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,3960.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,3960.248z" />
    				<g id="cross-2626" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3648.1,3914.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3680.4,3914.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2627" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,4019.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,4019.248z" />
    				<g id="cross-2627" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3648.3,3974.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3680.6,3974.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2628" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3642.876,4078.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3642.876,4078.248z" />
    				<g id="cross-2628" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3648.5,4033.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3680.8,4033.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 7 -->

    			<g id="seat-2629" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,2582.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,2582.248z" />
    				<g id="cross-2629" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.5,2536.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795.8,2537.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2630" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,2641.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,2641.248z" />
    				<g id="cross-2630" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.3,2595.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795.6,2596.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2631" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,2699.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,2699.248z" />
    				<g id="cross-2631" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.1,2653.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795.4,2653.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2632" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,2757.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,2757.248z" />
    				<g id="cross-2632" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.3,2711.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795.6,2711.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2633" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,2815.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,2815.248z" />
    				<g id="cross-2633" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3762.9,2769.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795.2,2769.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2634" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,2873.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,2873.248z" />
    				<g id="cross-2634" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.5,2827.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795.8,2827.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2635" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,2931.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,2931.248z" />
    				<g id="cross-2635" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.7,2886.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3796,2886.7c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2636" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,2989.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,2989.248z" />
    				<g id="cross-2636" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.9,2943.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3796.2,2943.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2637" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3047.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,3047.248z" />
    				<g id="cross-2637" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3762.7,3001.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795,3001.6c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2638" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3106.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,3106.248z" />
    				<g id="cross-2638" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3762.5,3061.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3794.8,3061.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2639" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3165.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,3165.248z" />
    				<g id="cross-2639" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3762.3,3119.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3794.6,3119.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2640" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3224.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3758.876,3224.248z" />
    				<g id="cross-2640" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3762.2,3178.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3794.5,3178.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 8 -->

    			<g id="seat-2641" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3552.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,3552.248z" />
    				<g id="cross-2641" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3762,3506.2c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3794.3,3506.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2642" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3610.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,3610.248z" />
    				<g id="cross-2642" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3762.2,3564.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3794.5,3564.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2643" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3669.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,3669.248z" />
    				<g id="cross-2643" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.5,3623.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795.8,3623.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2644" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3727.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,3727.248z" />
    				<g id="cross-2644" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.7,3681.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3796,3681.6c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2645" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3785.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,3785.248z" />
    				<g id="cross-2645" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.9,3740.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3796.2,3740.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2646" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3843.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,3843.248z" />
    				<g id="cross-2646" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3764.1,3798.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3796.4,3798.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2647" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3901.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,3901.248z" />
    				<g id="cross-2647" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3764.3,3856.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3796.6,3856.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2648" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,3960.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,3960.248z" />
    				<g id="cross-2648" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3764.5,3914.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3796.8,3914.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2649" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,4019.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,4019.248z" />
    				<g id="cross-2649" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3764.6,3974.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3796.9,3974.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2650" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,4078.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,4078.248z" />
    				<g id="cross-2650" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3763.3,4033.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3795.6,4033.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2651" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,4136.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,4136.248z" />
    				<g id="cross-2651" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3761.8,4090.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3794.1,4091.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2652" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3758.876,4195.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3758.876,4195.248z" />
    				<g id="cross-2652" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3761.6,4149.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3793.9,4150.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 9 -->

    			<g id="seat-2653" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2464.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2464.248z" />
    				<g id="cross-2653" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3868.6,2418.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3900.9,2419c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2654" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2523.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2523.248z" />
    				<g id="cross-2654" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3868.8,2476.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3901.1,2477c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2655" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2582.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2582.248z" />
    				<g id="cross-2655" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.2,2535.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.5,2536c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2656" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2641.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2641.248z" />
    				<g id="cross-2656" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.3,2593.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.6,2594c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2657" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2699.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2699.248z" />
    				<g id="cross-2657" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.5,2652.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.8,2653.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2658" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2757.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2757.248z" />
    				<g id="cross-2658" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.7,2710.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3903,2711.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2659" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2815.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2815.248z" />
    				<g id="cross-2659" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.9,2768.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3903.2,2769.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2660" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2873.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2873.248z" />
    				<g id="cross-2660" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3871.1,2826.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3903.4,2827c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2661" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2931.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2931.248z" />
    				<g id="cross-2661" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3871.3,2886.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3903.6,2887.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2662" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,2989.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,2989.248z" />
    				<g id="cross-2662" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870,2945.8c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.3,2946.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2663" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3047.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,3047.248z" />
    				<g id="cross-2663" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3868.4,3003.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3900.7,3003.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2664" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3106.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,3106.248z" />
    				<g id="cross-2664" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3868.2,3062.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3900.5,3062.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2665" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3165.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,3165.248z" />
    				<g id="cross-2665" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3868,3119c13.9,13.9,31.9,31.9,31.9,31.9"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3900.3,3119.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2666" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3224.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3866.876,3224.248z" />
    				<g id="cross-2666" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3867.9,3178c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3900.2,3178.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 10 -->

    			<g id="seat-2667" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3552.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,3552.248z" />
    				<g id="cross-2667" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.5,3507.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.8,3507.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2668" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3610.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,3610.248z" />
    				<g id="cross-2668" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.7,3565.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3903,3565.7c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2669" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3669.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,3669.248z" />
    				<g id="cross-2669" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3872.1,3624.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3904.4,3624.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2670" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3727.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,3727.248z" />
    				<g id="cross-2670" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3872.3,3682.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3904.6,3682.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2671" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3785.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,3785.248z" />
    				<g id="cross-2671" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3872.5,3741.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3904.8,3741.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2672" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3843.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,3843.248z" />
    				<g id="cross-2672" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3872.6,3799.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3904.9,3799.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2673" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3901.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,3901.248z" />
    				<g id="cross-2673" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3872.8,3857.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3905.1,3857.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2674" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,3960.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,3960.248z" />
    				<g id="cross-2674" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3873,3915.3c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3905.3,3915.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2675" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,4019.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,4019.248z" />
    				<g id="cross-2675" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3873.2,3975.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3905.5,3975.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2676" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,4078.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,4078.248z" />
    				<g id="cross-2676" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3871.9,4034.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3904.2,4034.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2677" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,4136.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,4136.248z" />
    				<g id="cross-2677" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.3,4091.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.6,4092.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2678" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,4195.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,4195.248z" />
    				<g id="cross-2678" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870.2,4150.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.5,4151.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2679" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,4254.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,4254.248z" />
    				<g id="cross-2679" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3870,4207.7c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.3,4208.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2680" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3866.876,4313.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3866.876,4313.248z" />
    				<g id="cross-2680" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3869.8,4266.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3902.1,4267.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 11 -->

    			<g id="seat-2681" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2346.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2346.248z" />
    				<g id="cross-2681" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3984.8,2300.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4017.1,2301.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2682" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2405.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2405.248z" />
    				<g id="cross-2682" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3985,2358.7c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4017.3,2359.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2683" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2464.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2464.248z" />
    				<g id="cross-2683" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.3,2417.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4018.6,2418.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2684" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2523.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2523.248z" />
    				<g id="cross-2684" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.5,2475.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4018.8,2476.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2685" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2582.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2582.248z" />
    				<g id="cross-2685" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.7,2534.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019,2535.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2686" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2641.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2641.248z" />
    				<g id="cross-2686" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.9,2592.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.2,2593.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2687" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2699.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2699.248z" />
    				<g id="cross-2687" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3987.1,2650.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.4,2651.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2688" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2757.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2757.248z" />
    				<g id="cross-2688" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3987.3,2708.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.6,2709.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2689" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2815.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2815.248z" />
    				<g id="cross-2689" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3987.5,2768.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.8,2769.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2690" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2873.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2873.248z" />
    				<g id="cross-2690" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.1,2827.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4018.4,2828.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2691" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2931.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2931.248z" />
    				<g id="cross-2691" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3984.6,2885.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4016.9,2885.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2692" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,2989.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,2989.248z" />
    				<g id="cross-2692" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3984.4,2944.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4016.7,2944.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2693" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,3047.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,3047.248z" />
    				<g id="cross-2693" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3984.2,3001.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4016.5,3001.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2694" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,3106.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,3106.248z" />
    				<g id="cross-2694" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3984,3060.1c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4016.3,3060.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2695" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,3165.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,3165.248z" />
    				<g id="cross-2695" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3983.8,3118.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4016.1,3119.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2696" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3982.876,3224.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L3982.876,3224.248z" />
    				<g id="cross-2696" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3983.6,3177.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4015.9,3178.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 12 -->

    			<g id="seat-2697" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,3552.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,3552.248z" />
    				<g id="cross-2697" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3987.4,3506.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.7,3506.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2698" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,3610.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,3610.248z" />
    				<g id="cross-2698" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3987.6,3564.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.9,3564.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2699" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,3669.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,3669.248z" />
    				<g id="cross-2699" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3989,3623.2c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4021.3,3623.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2700" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,3727.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,3727.248z" />
    				<g id="cross-2700" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3989.2,3681.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4021.5,3681.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2701" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,3785.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,3785.248z" />
    				<g id="cross-2701" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3989.3,3740.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4021.6,3740.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2702" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,3843.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,3843.248z" />
    				<g id="cross-2702" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3989.5,3798.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4021.8,3798.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2703" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,3901.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,3901.248z" />
    				<g id="cross-2703" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3989.7,3856.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4022,3856.7c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2704" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,3960.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,3960.248z" />
    				<g id="cross-2704" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3989.9,3914.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4022.2,3914.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2705" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,4019.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,4019.248z" />
    				<g id="cross-2705" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3990.1,3974.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4022.4,3974.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2706" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,4078.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,4078.248z" />
    				<g id="cross-2706" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3988.8,4033.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4021.1,4033.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2707" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,4136.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,4136.248z" />
    				<g id="cross-2707" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3987.2,4090.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.5,4091.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2708" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,4195.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,4195.248z" />
    				<g id="cross-2708" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3987,4149.8c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.3,4150.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2709" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,4254.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,4254.248z" />
    				<g id="cross-2709" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.9,4206.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019.2,4206.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2710" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,4313.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,4313.248z" />
    				<g id="cross-2710" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.7,4265.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4019,4265.9c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2711" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,4372.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,4372.248z" />
    				<g id="cross-2711" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.5,4324.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4018.8,4324.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2712" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3983.876,4430.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L3983.876,4430.248z" />
    				<g id="cross-2712" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3986.3,4383.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4018.6,4383.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 13 -->

    			<g id="seat-2713" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2228.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2228.248z" />
    				<g id="cross-2713" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4088.7,2182c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4121,2182.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2714" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2287.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2287.248z" />
    				<g id="cross-2714" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4088.9,2240c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4121.2,2240.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2715" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2346.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2346.248z" />
    				<g id="cross-2715" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4090.3,2299c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.6,2299.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2716" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2405.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2405.248z" />
    				<g id="cross-2716" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4090.5,2359c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.8,2359.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2717" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2464.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2464.248z" />
    				<g id="cross-2717" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4090.6,2417.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.9,2417.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2718" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2523.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2523.248z" />
    				<g id="cross-2718" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4089.8,2477.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.1,2477.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2719" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2582.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2582.248z" />
    				<g id="cross-2719" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4090,2535.2c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.3,2535.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2720" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2641.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2641.248z" />
    				<g id="cross-2720" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4089.2,2596c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4121.5,2596.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2721" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2699.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2699.248z" />
    				<g id="cross-2721" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4090.4,2653.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.7,2653.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2722" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2757.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2757.248z" />
    				<g id="cross-2722" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4090.1,2709.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.4,2709.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2723" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2815.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2815.248z" />
    				<g id="cross-2723" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4088.5,2768.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4120.8,2769c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2724" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2873.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2873.248z" />
    				<g id="cross-2724" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4088.3,2826.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4120.6,2827c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2725" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2931.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2931.248z" />
    				<g id="cross-2725" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4089.2,2883.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4121.5,2883.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2726" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,2989.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,2989.248z" />
    				<g id="cross-2726" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4090,2941.4c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.3,2941.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2727" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,3047.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,3047.248z" />
    				<g id="cross-2727" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4089.8,3000.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4122.1,3000.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2728" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,3106.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,3106.248z" />
    				<g id="cross-2728" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4089.6,3059.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4121.9,3059.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2729" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,3165.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,3165.248z" />
    				<g id="cross-2729" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4089.4,3118.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4121.7,3119c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2730" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4086.876,3224.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4086.876,3224.248z" />
    				<g id="cross-2730" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4089.2,3177.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4121.5,3178c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>

    			<!-- B ROW 14 -->

    			<g id="seat-2731" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,3552.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,3552.248z" />
    				<g id="cross-2731" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4096.7,3507.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4129,3508.1c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2732" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,3610.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,3610.248z" />
    				<g id="cross-2732" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4096.9,3565.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4129.2,3566.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2733" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,3669.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,3669.248z" />
    				<g id="cross-2733" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4098.3,3624.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.6,3625.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2734" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,3727.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,3727.248z" />
    				<g id="cross-2734" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4098.5,3684.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.8,3685.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2735" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,3785.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,3785.248z" />
    				<g id="cross-2735" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4098.6,3742.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.9,3743.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2736" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,3843.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,3843.248z" />
    				<g id="cross-2736" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4097.8,3802.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.1,3803.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2737" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,3901.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,3901.248z" />
    				<g id="cross-2737" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4098,3860.9c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.3,3861.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2738" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,3960.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,3960.248z" />
    				<g id="cross-2738" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4097.2,3921.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4129.5,3922.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2739" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4019.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4019.248z" />
    				<g id="cross-2739" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4098.4,3978.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.7,3979.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2740" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4078.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4078.248z" />
    				<g id="cross-2740" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4098.1,4034.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.4,4035.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2741" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4136.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4136.248z" />
    				<g id="cross-2741" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4096.5,4094.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4128.8,4094.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2742" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4195.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4195.248z" />
    				<g id="cross-2742" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4096.3,4152.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4128.6,4152.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2743" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4254.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4254.248z" />
    				<g id="cross-2743" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4097.2,4209.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4129.5,4209.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2744" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4313.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4313.248z" />
    				<g id="cross-2744" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4098,4267.1c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.3,4267.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2745" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4372.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4372.248z" />
    				<g id="cross-2745" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4097.8,4325.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4130.1,4326.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2746" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4430.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4430.248z" />
    				<g id="cross-2746" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4097.6,4384.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4129.9,4385.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2747" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4489.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4489.248z" />
    				<g id="cross-2747" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4097.4,4444.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4129.7,4444.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2748" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4092.876,4548.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4092.876,4548.248z" />
    				<g id="cross-2748" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4097.2,4503.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4129.5,4503.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 15 -->

    			<g id="seat-2749" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2110.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2110.248z" />
    				<g id="cross-2749" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4221.7,2063.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4254,2063.7c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2750" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2168.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2168.248z" />
    				<g id="cross-2750" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4221.9,2121.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4254.2,2121.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2751" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2227.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2227.248z" />
    				<g id="cross-2751" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.3,2180.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.6,2180.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2752" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2285.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2285.248z" />
    				<g id="cross-2752" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.5,2240.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.8,2240.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2753" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2343.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2343.248z" />
    				<g id="cross-2753" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.6,2298.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.9,2298.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2754" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2401.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2401.248z" />
    				<g id="cross-2754" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4222.8,2358.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.1,2358.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2755" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2459.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2459.248z" />
    				<g id="cross-2755" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223,2416.5c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.3,2416.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2756" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2518.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2518.248z" />
    				<g id="cross-2756" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4222.2,2477.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4254.5,2477.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2757" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2577.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2577.248z" />
    				<g id="cross-2757" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.4,2534.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.7,2534.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2758" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2636.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2636.248z" />
    				<g id="cross-2758" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.1,2590.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.4,2590.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2759" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2694.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2694.248z" />
    				<g id="cross-2759" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4221.5,2649.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4253.8,2650.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2760" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2753.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2753.248z" />
    				<g id="cross-2760" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4221.3,2707.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4253.6,2708.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2761" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2812.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2812.248z" />
    				<g id="cross-2761" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4222.2,2764.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4254.5,2765.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2762" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2871.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2871.248z" />
    				<g id="cross-2762" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223,2822.7c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.3,2823.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2763" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2930.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2930.248z" />
    				<g id="cross-2763" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4222.8,2881.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.1,2881.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2764" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,2988.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,2988.248z" />
    				<g id="cross-2764" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4222.6,2940.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4254.9,2940.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2765" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3047.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,3047.248z" />
    				<g id="cross-2765" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4222.4,2999.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4254.7,3000.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2766" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3106.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,3106.248z" />
    				<g id="cross-2766" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4222.2,3058.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4254.5,3059.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2767" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3165.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,3165.248z" />
    				<g id="cross-2767" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.2,3118.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.5,3118.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2768" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3224.248
    				c-1.78,0.009-4.566,0.114-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.841c-0.012-1.884-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.333,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.768,0.247,25.036-13.546,29.213L4219.876,3224.248z" />
    				<g id="cross-2768" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.3,3177.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.6,3177.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- B ROW 16 -->

    			<g id="seat-2769" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3552.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,3552.248z" />
    				<g id="cross-2769" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.7,3508.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4256,3508.5c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2770" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3610.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,3610.248z" />
    				<g id="cross-2770" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.9,3566.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4256.2,3566.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2771" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3669.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,3669.248z" />
    				<g id="cross-2771" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225.3,3625.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.6,3625.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2772" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3727.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,3727.248z" />
    				<g id="cross-2772" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225.5,3685.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.8,3685.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2773" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3785.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,3785.248z" />
    				<g id="cross-2773" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225.6,3743.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.9,3743.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2774" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3843.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,3843.248z" />
    				<g id="cross-2774" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4224.8,3803.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.1,3803.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2775" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3901.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,3901.248z" />
    				<g id="cross-2775" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225,3861.3c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.3,3861.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2776" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,3960.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,3960.248z" />
    				<g id="cross-2776" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4224.2,3922.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4256.5,3922.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2777" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4019.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4019.248z" />
    				<g id="cross-2777" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225.4,3979.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.7,3979.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2778" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4078.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4078.248z" />
    				<g id="cross-2778" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225.1,4035.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.4,4035.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2779" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4136.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4136.248z" />
    				<g id="cross-2779" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.5,4094.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.8,4095.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2780" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4195.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4195.248z" />
    				<g id="cross-2780" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4223.3,4152.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4255.6,4153.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2781" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4254.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4254.248z" />
    				<g id="cross-2781" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4224.2,4209.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4256.5,4209.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2782" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4313.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4313.248z" />
    				<g id="cross-2782" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225,4267.5c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.3,4267.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2783" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4372.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4372.248z" />
    				<g id="cross-2783" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4224.8,4326.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.1,4326.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2784" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4430.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4430.248z" />
    				<g id="cross-2784" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4224.6,4385.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4256.9,4385.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2785" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4489.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4489.248z" />
    				<g id="cross-2785" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4224.4,4444.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4256.7,4445.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2786" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4548.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4548.248z" />
    				<g id="cross-2786" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4224.2,4503.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4256.5,4504.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2787" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4607.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4607.248z" />
    				<g id="cross-2787" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225.2,4563.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.5,4563.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2788" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M4219.876,4666.248
    				c-1.78,0.009-4.566,0.113-5.738-1.115c-1.177-1.229-0.736-3.791-0.748-5.678l-0.257-44.842c-0.012-1.885-0.478-4.279,0.681-5.521
    				c1.161-1.243,3.944-1.332,5.728-1.343l34.379-0.198c15.722,6.282,14.29,25.51,14.311,29.284l0,0
    				c0.022,3.769,0.247,25.036-13.546,29.213L4219.876,4666.248z" />
    				<g id="cross-2788" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4225.3,4622.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M4257.6,4622.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- SECTION C -->

    			<!-- C ROW 1 -->

    			<g id="seat-2789" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3172.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3172.457,4231.211z" />
    				<g id="cross-2789" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3185.7,4232.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3218,4233.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>

    			</g>
    			<g id="seat-2790" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3113.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3113.457,4231.211z" />
    				<g id="cross-2790" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3126.5,4232.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3158.8,4233c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2791" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3054.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3054.457,4231.211z" />
    				<g id="cross-2791" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3067.7,4232.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3100,4233c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2792" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2995.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2995.457,4231.211z" />
    				<g id="cross-2792" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3008.7,4232.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3041,4232.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2793" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2936.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2936.457,4231.211z" />
    				<g id="cross-2793" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.7,4233c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2982,4233.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2794" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2877.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2877.457,4231.211z" />
    				<g id="cross-2794" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2890.7,4233.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2923,4233.6c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2795" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2818.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2818.457,4231.211z" />
    				<g id="cross-2795" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.7,4233.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2864,4233.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2796" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2759.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2759.457,4231.211z" />
    				<g id="cross-2796" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.7,4232.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2805,4232.6c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2797" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2700.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2700.457,4231.211z" />
    				<g id="cross-2797" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2713.7,4233.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2746,4234c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2798" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2641.457,4231.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2641.457,4231.211z" />
    				<g id="cross-2798" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2654.7,4233.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2687,4234.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>

    			<!-- C ROW 2 -->

    			<g id="seat-2799" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2308.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2308.457,4228.211z" />
    				<g id="cross-2799" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2321.8,4230.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2354.1,4230.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2800" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2249.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2249.457,4228.211z" />
    				<g id="cross-2800" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2262.6,4230.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2294.9,4230.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2801" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2190.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2190.457,4228.211z" />
    				<g id="cross-2801" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2203.8,4230.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2236.1,4230.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2802" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2131.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2131.457,4228.211z" />
    				<g id="cross-2802" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2144.8,4229.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2177.1,4230.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2803" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2072.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2072.457,4228.211z" />
    				<g id="cross-2803" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2085.8,4230.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2118.1,4230.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2804" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2013.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2013.457,4228.211z" />
    				<g id="cross-2804" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2026.8,4230.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2059.1,4231.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2805" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1954.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1954.457,4228.211z" />
    				<g id="cross-2805" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1967.8,4230.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2000.1,4231.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2806" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1895.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1895.457,4228.211z" />
    				<g id="cross-2806" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1908.8,4229.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1941.1,4230.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2807" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1837.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1837.457,4228.211z" />
    				<g id="cross-2807" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1849.8,4231.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1882.1,4231.5
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2808" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1778.457,4228.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1778.457,4228.211z" />
    				<g id="cross-2808" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1790.8,4231.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1823.1,4231.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- C ROW 3 -->

    			<g id="seat-2809" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3290.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3290.457,4349.211z" />
    				<g id="cross-2809" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3303.8,4353.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3336.1,4354c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2810" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3231.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3231.457,4349.211z" />
    				<g id="cross-2810" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3244.6,4353.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3276.9,4353.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2811" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3172.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3172.457,4349.211z" />
    				<g id="cross-2811" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3185.8,4353.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3218.1,4353.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2812" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3113.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3113.457,4349.211z" />
    				<g id="cross-2812" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3126.8,4353.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3159.1,4353.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2813" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3054.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3054.457,4349.211z" />
    				<g id="cross-2813" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3067.8,4353.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3100.1,4354.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2814" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2995.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2995.457,4349.211z" />
    				<g id="cross-2814" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3008.8,4354c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3041.1,4354.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2815" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2936.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2936.457,4349.211z" />
    				<g id="cross-2815" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.8,4354.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2982.1,4354.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2816" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2877.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2877.457,4349.211z" />
    				<g id="cross-2816" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2890.8,4353.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2923.1,4353.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2817" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2818.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2818.457,4349.211z" />
    				<g id="cross-2817" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.8,4354.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2864.1,4354.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2818" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2759.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2759.457,4349.211z" />
    				<g id="cross-2818" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.8,4354.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2805.1,4355c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2819" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2700.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2700.457,4349.211z" />
    				<g id="cross-2819" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2713.5,4352.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2745.8,4353.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2820" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2641.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2641.457,4349.211z" />
    				<g id="cross-2820" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2654.8,4352.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2687.1,4353.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- C ROW 4 -->

    			<g id="seat-2821" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2308.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2308.457,4349.211z" />
    				<g id="cross-2821" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2321.5,4353.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2353.8,4354.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2822" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2249.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2249.457,4349.211z" />
    				<g id="cross-2822" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2262.3,4353.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2294.6,4354c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2823" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2190.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2190.457,4349.211z" />
    				<g id="cross-2823" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2203.5,4353.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2235.8,4354c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2824" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2131.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2131.457,4349.211z" />
    				<g id="cross-2824" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2144.5,4353.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2176.8,4353.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2825" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2072.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2072.457,4349.211z" />
    				<g id="cross-2825" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2085.5,4354c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2117.8,4354.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2826" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2013.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2013.457,4349.211z" />
    				<g id="cross-2826" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2026.5,4354.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2058.8,4354.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2827" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1954.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1954.457,4349.211z" />
    				<g id="cross-2827" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1967.5,4354.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1999.8,4354.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2828" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1895.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1895.457,4349.211z" />
    				<g id="cross-2828" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1908.5,4353.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1940.8,4353.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2829" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1837.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1837.457,4349.211z" />
    				<g id="cross-2829" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1849.5,4354.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1881.8,4355c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2830" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1778.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1778.457,4349.211z" />
    				<g id="cross-2830" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1790.5,4354.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1822.8,4355.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2831" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1719.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1719.457,4349.211z" />
    				<g id="cross-2831" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1731.1,4353.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1763.4,4353.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2832" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1660.457,4349.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1660.457,4349.211z" />
    				<g id="cross-2832" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1672.5,4352.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1704.8,4353.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- C ROW 5 -->

    			<g id="seat-2833" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3407.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3407.457,4454.211z" />
    				<g id="cross-2833" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3421.8,4458.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3454.1,4459c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2834" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3348.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3348.457,4454.211z" />
    				<g id="cross-2834" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3362.6,4458.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3394.9,4458.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2835" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3290.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3290.457,4454.211z" />
    				<g id="cross-2835" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3303.8,4458.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3336.1,4458.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2836" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3231.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3231.457,4454.211z" />
    				<g id="cross-2836" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3244.8,4458.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3277.1,4458.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2837" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3172.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3172.457,4454.211z" />
    				<g id="cross-2837" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3185.8,4458.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3218.1,4459.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2838" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3113.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3113.457,4454.211z" />
    				<g id="cross-2838" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3126.8,4459c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3159.1,4459.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2839" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3054.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3054.457,4454.211z" />
    				<g id="cross-2839" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3067.8,4459.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3100.1,4459.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2840" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2995.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2995.457,4454.211z" />
    				<g id="cross-2840" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3008.8,4458.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3041.1,4458.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2841" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2936.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2936.457,4454.211z" />
    				<g id="cross-2841" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.8,4459.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2982.1,4459.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2842" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2877.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2877.457,4454.211z" />
    				<g id="cross-2842" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2890.8,4459.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2923.1,4460c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2843" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2818.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2818.457,4454.211z" />
    				<g id="cross-2843" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.4,4457.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2863.7,4458.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2844" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2759.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2759.457,4454.211z" />
    				<g id="cross-2844" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.8,4457.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2805.1,4458.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2845" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2700.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2700.457,4454.211z" />
    				<g id="cross-2845" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2713.3,4457.5c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2745.6,4457.9
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2846" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2641.457,4454.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2641.457,4454.211z" />
    				<g id="cross-2846" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2655,4457.3c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2687.3,4457.7
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- C ROW 6 -->

    			<g id="seat-2847" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2308.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2308.457,4461.211z" />
    				<g id="cross-2847" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2321.7,4466c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2354,4466.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2848" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2249.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2249.457,4461.211z" />
    				<g id="cross-2848" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2262.5,4465.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2294.8,4466.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2849" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2190.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2190.457,4461.211z" />
    				<g id="cross-2849" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2203.7,4465.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2236,4466.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2850" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2131.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2131.457,4461.211z" />
    				<g id="cross-2850" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2144.7,4465.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2177,4466c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2851" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2072.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2072.457,4461.211z" />
    				<g id="cross-2851" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2085.7,4466.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2118,4466.6c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2852" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2013.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2013.457,4461.211z" />
    				<g id="cross-2852" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2026.7,4466.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2059,4466.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2853" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1954.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1954.457,4461.211z" />
    				<g id="cross-2853" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1967.7,4466.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2000,4467c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2854" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1895.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1895.457,4461.211z" />
    				<g id="cross-2854" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1908.7,4465.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1941,4465.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2855" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1837.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1837.457,4461.211z" />
    				<g id="cross-2855" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1849.7,4466.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1882,4467.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2856" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1778.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1778.457,4461.211z" />
    				<g id="cross-2856" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1790.7,4467c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1823,4467.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2857" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1719.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1719.457,4461.211z" />
    				<g id="cross-2857" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1731.3,4465.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1763.6,4465.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2858" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1660.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1660.457,4461.211z" />
    				<g id="cross-2858" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1672.7,4465.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1705,4465.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2859" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1601.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1601.457,4461.211z" />
    				<g id="cross-2859" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1613.2,4464.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1645.5,4465.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2860" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1542.457,4461.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1542.457,4461.211z" />
    				<g id="cross-2860" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1554.9,4464.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1587.2,4465.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- C ROW 7 -->

    			<g id="seat-2861" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3407.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3407.457,4576.211z" />
    				<g id="cross-2861" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3421.4,4581c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3453.7,4581.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2862" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3348.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3348.457,4576.211z" />
    				<g id="cross-2862" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3362.2,4580.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3394.5,4581.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2863" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3290.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3290.457,4576.211z" />
    				<g id="cross-2863" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3303.4,4580.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3335.7,4581.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2864" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3231.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3231.457,4576.211z" />
    				<g id="cross-2864" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3244.4,4580.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3276.7,4581c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2865" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3172.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3172.457,4576.211z" />
    				<g id="cross-2865" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3185.4,4581.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3217.7,4581.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2866" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3113.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3113.457,4576.211z" />
    				<g id="cross-2866" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3126.4,4581.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3158.7,4581.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2867" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3054.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3054.457,4576.211z" />
    				<g id="cross-2867" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3067.4,4581.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3099.7,4582c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2868" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2995.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2995.457,4576.211z" />
    				<g id="cross-2868" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3008.4,4580.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3040.7,4580.8
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2869" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2936.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2936.457,4576.211z" />
    				<g id="cross-2869" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.4,4581.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2981.7,4582.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2870" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2877.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2877.457,4576.211z" />
    				<g id="cross-2870" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2890.4,4582c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2922.7,4582.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2871" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2818.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2818.457,4576.211z" />
    				<g id="cross-2871" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831,4580.3c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2863.3,4580.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2872" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2759.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2759.457,4576.211z" />
    				<g id="cross-2872" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.4,4580.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2804.7,4580.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2873" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2700.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2700.457,4576.211z" />
    				<g id="cross-2873" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2712.9,4579.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2745.2,4580.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2874" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2641.457,4576.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2641.457,4576.211z" />
    				<g id="cross-2874" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2654.6,4579.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2686.9,4580.1C2673,4594,2655,4612,2655,4612
    						"/>
    				</g>
    			</g>

    			<!-- C ROW 8 -->

    			<g id="seat-2875" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2308.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2308.457,4577.211z" />
    				<g id="cross-2875" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2321.7,4581c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2354,4581.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2876" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2249.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2249.457,4577.211z" />
    				<g id="cross-2876" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2262.5,4580.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2294.8,4581.2
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2877" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2190.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2190.457,4577.211z" />
    				<g id="cross-2877" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2203.7,4580.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2236,4581.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2878" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2131.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2131.457,4577.211z" />
    				<g id="cross-2878" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2144.7,4580.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2177,4581c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2879" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2072.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2072.457,4577.211z" />
    				<g id="cross-2879" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2085.7,4581.2c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2118,4581.6c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2880" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2013.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2013.457,4577.211z" />
    				<g id="cross-2880" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2026.7,4581.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2059,4581.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2881" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1954.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1954.457,4577.211z" />
    				<g id="cross-2881" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1967.7,4581.6c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2000,4582c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2882" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1895.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1895.457,4577.211z" />
    				<g id="cross-2882" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1908.7,4580.4c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1941,4580.8c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2883" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1837.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1837.457,4577.211z" />
    				<g id="cross-2883" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1849.7,4581.8c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1882,4582.2c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2884" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1778.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1778.457,4577.211z" />
    				<g id="cross-2884" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1790.7,4582c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1823,4582.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2885" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1719.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1719.457,4577.211z" />
    				<g id="cross-2885" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1731.3,4580.3c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1763.6,4580.6
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2886" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1660.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1660.457,4577.211z" />
    				<g id="cross-2886" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1672.7,4580.1c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1705,4580.4c-13.9,13.9-31.9,31.9-31.9,31.9"
    						/>
    				</g>
    			</g>
    			<g id="seat-2887" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1601.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1601.457,4577.211z" />
    				<g id="cross-2887" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1613.2,4579.9c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1645.5,4580.3
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2888" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1542.457,4577.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1542.457,4577.211z" />
    				<g id="cross-2888" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1554.9,4579.7c13.9,13.9,31.9,31.9,31.9,31.9
    						"/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1587.2,4580.1
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>

    			<!-- C ROW 9 -->

    			<g id="seat-2889" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3407.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3407.457,4700.211z" />
    				<g id="cross-2889" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3421.4,4705c13.9,13.9,31.9,31.9,31.9,31.9"
    						/>
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3453.7,4705.4
    						c-13.9,13.9-31.9,31.9-31.9,31.9"/>
    				</g>
    			</g>
    			<g id="seat-2890" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3348.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3348.457,4700.211z" />
    				<g id="cross-2890" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3362.2,4704.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3394.5,4705.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2891" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3290.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3290.457,4700.211z" />
    				<g id="cross-2891" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3303.4,4704.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3335.7,4705.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2892" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3231.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3231.457,4700.211z" />
    				<g id="cross-2892" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3244.4,4704.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3276.7,4705c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2893" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3172.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3172.457,4700.211z" />
    				<g id="cross-2893" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3185.4,4705.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3217.7,4705.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2894" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3113.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3113.457,4700.211z" />
    				<g id="cross-2894" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3126.4,4705.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3158.7,4705.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2895" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3054.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3054.457,4700.211z" />
    				<g id="cross-2895" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3067.4,4705.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3099.7,4706c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2896" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2995.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2995.457,4700.211z" />
    				<g id="cross-2896" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3008.4,4704.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3040.7,4704.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2897" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2936.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2936.457,4700.211z" />
    				<g id="cross-2897" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.4,4705.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2981.7,4706.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2898" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2877.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2877.457,4700.211z" />
    				<g id="cross-2898" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2890.4,4706c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2922.7,4706.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2899" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2818.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2818.457,4700.211z" />
    				<g id="cross-2899" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2831,4704.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2863.3,4704.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2900" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2759.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2759.457,4700.211z" />
    				<g id="cross-2900" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.4,4704.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2804.7,4704.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2901" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2700.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2700.457,4700.211z" />
    				<g id="cross-2901" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2712.9,4703.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2745.2,4704.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2902" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2641.457,4700.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2641.457,4700.211z" />
    				<g id="cross-2902" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2654.6,4703.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2686.9,4704.1C2673,4718,2655,4736,2655,4736
    					" />
    				</g>
    			</g>

    			<!-- C ROW 10 -->

    			<g id="seat-2903" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2308.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2308.457,4701.211z" />
    				<g id="cross-2903" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2321.7,4705.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2354,4706c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2904" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2249.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2249.457,4701.211z" />
    				<g id="cross-2904" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2262.5,4705.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2294.8,4705.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2905" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2190.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2190.457,4701.211z" />
    				<g id="cross-2905" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2203.7,4705.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2236,4705.8c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2906" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2131.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2131.457,4701.211z" />
    				<g id="cross-2906" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2144.7,4705.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2177,4705.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2907" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2072.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2072.457,4701.211z" />
    				<g id="cross-2907" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2085.7,4705.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2118,4706.2c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2908" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2013.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2013.457,4701.211z" />
    				<g id="cross-2908" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2026.7,4706c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2059,4706.4c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2909" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1954.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1954.457,4701.211z" />
    				<g id="cross-2909" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1967.7,4706.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2000,4706.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2910" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1895.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1895.457,4701.211z" />
    				<g id="cross-2910" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1908.7,4705c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1941,4705.4c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2911" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1837.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1837.457,4701.211z" />
    				<g id="cross-2911" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1849.7,4706.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1882,4706.7c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2912" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1778.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1778.457,4701.211z" />
    				<g id="cross-2912" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1790.7,4706.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1823,4706.9c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2913" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1719.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1719.457,4701.211z" />
    				<g id="cross-2913" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1731.3,4704.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1763.6,4705.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2914" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1660.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1660.457,4701.211z" />
    				<g id="cross-2914" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1672.7,4704.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1705,4705c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2915" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1601.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1601.457,4701.211z" />
    				<g id="cross-2915" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1613.2,4704.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1645.5,4704.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2916" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1542.457,4701.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1542.457,4701.211z" />
    				<g id="cross-2916" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1554.9,4704.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1587.2,4704.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- C ROW 11 -->

    			<g id="seat-2917" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3525.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3525.457,4826.211z" />
    				<g id="cross-2917" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3539.9,4831c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3572.2,4831.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2918" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3466.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3466.457,4826.211z" />
    				<g id="cross-2918" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3480.7,4830.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3513,4831.2c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2919" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3407.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3407.457,4826.211z" />
    				<g id="cross-2919" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3421.9,4830.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3454.2,4831.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2920" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3348.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3348.457,4826.211z" />
    				<g id="cross-2920" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3362.9,4830.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3395.2,4831c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2921" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3290.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3290.457,4826.211z" />
    				<g id="cross-2921" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3303.9,4831.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3336.2,4831.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2922" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3231.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3231.457,4826.211z" />
    				<g id="cross-2922" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3244.9,4831.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3277.2,4831.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2923" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3172.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3172.457,4826.211z" />
    				<g id="cross-2923" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3185.9,4831.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3218.2,4832c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2924" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3113.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3113.457,4826.211z" />
    				<g id="cross-2924" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3126.9,4830.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3159.2,4830.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2925" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3054.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3054.457,4826.211z" />
    				<g id="cross-2925" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3067.9,4831.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3100.2,4832.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2926" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2995.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2995.457,4826.211z" />
    				<g id="cross-2926" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3008.9,4832c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3041.2,4832.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2927" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2936.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2936.457,4826.211z" />
    				<g id="cross-2927" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.6,4830.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2981.9,4830.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2928" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2877.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2877.457,4826.211z" />
    				<g id="cross-2928" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2891,4830.1c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2923.3,4830.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2929" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2818.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2818.457,4826.211z" />
    				<g id="cross-2929" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.4,4829.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2863.7,4830.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2930" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2759.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2759.457,4826.211z" />
    				<g id="cross-2930" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2773.2,4829.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2805.5,4830.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2931" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2700.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2700.457,4826.211z" />
    				<g id="cross-2931" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2713.8,4829.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2746.1,4829.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2932" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2641.457,4826.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2641.457,4826.211z" />
    				<g id="cross-2932" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2654.4,4829.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2686.7,4829.7
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- C ROW 12 -->

    			<g id="seat-2933" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2308.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2308.457,4827.211z" />
    				<g id="cross-2933" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2322.7,4832.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2355,4832.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2934" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2249.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2249.457,4827.211z" />
    				<g id="cross-2934" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2263.6,4832c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2295.9,4832.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2935" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2190.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2190.457,4827.211z" />
    				<g id="cross-2935" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2204.7,4832c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2237,4832.4c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2936" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2131.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2131.457,4827.211z" />
    				<g id="cross-2936" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2145.7,4831.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2178,4832.2c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2937" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2072.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2072.457,4827.211z" />
    				<g id="cross-2937" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2086.7,4832.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2119,4832.8c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2938" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2013.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2013.457,4827.211z" />
    				<g id="cross-2938" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2027.7,4832.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2060,4833c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2939" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1954.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1954.457,4827.211z" />
    				<g id="cross-2939" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1968.7,4832.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2001,4833.2c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2940" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1895.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1895.457,4827.211z" />
    				<g id="cross-2940" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1909.7,4831.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1942,4832c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2941" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1837.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1837.457,4827.211z" />
    				<g id="cross-2941" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1850.7,4833c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1883,4833.4c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2942" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1778.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1778.457,4827.211z" />
    				<g id="cross-2942" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1791.7,4833.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1824,4833.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2943" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1719.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1719.457,4827.211z" />
    				<g id="cross-2943" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1732.4,4831.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1764.7,4831.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2944" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1660.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1660.457,4827.211z" />
    				<g id="cross-2944" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1673.8,4831.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1706.1,4831.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2945" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1601.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1601.457,4827.211z" />
    				<g id="cross-2945" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1614.2,4831.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1646.5,4831.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2946" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1542.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1542.457,4827.211z" />
    				<g id="cross-2946" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1556,4830.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1588.3,4831.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2947" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1483.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1483.457,4827.211z" />
    				<g id="cross-2947" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1496.7,4830.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1529,4831.1C1515,4845,1497,4863,1497,4863" />
    				</g>
    			</g>
    			<g id="seat-2948" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1424.457,4827.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1424.457,4827.211z" />
    				<g id="cross-2948" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1437.3,4830.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1469.6,4830.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- C ROW 13 -->

    			<g id="seat-2949" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3643.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3643.457,4932.211z" />
    				<g id="cross-2949" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3658,4936.6c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3690.3,4937c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2950" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3584.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3584.457,4932.211z" />
    				<g id="cross-2950" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3598.9,4936.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3631.2,4936.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2951" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3525.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3525.457,4932.211z" />
    				<g id="cross-2951" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3540,4936.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3572.3,4936.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2952" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3466.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3466.457,4932.211z" />
    				<g id="cross-2952" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3481,4936.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3513.3,4936.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2953" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3407.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3407.457,4932.211z" />
    				<g id="cross-2953" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3422,4936.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3454.3,4937.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2954" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3348.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3348.457,4932.211z" />
    				<g id="cross-2954" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3363,4937c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3395.3,4937.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2955" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3290.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3290.457,4932.211z" />
    				<g id="cross-2955" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3304,4937.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3336.3,4937.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2956" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3231.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3231.457,4932.211z" />
    				<g id="cross-2956" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3245,4936.1c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3277.3,4936.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2957" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3172.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3172.457,4932.211z" />
    				<g id="cross-2957" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3186,4937.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3218.3,4937.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2958" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3113.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3113.457,4932.211z" />
    				<g id="cross-2958" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3127,4937.6c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3159.3,4938c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2959" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3054.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3054.457,4932.211z" />
    				<g id="cross-2959" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3067.7,4935.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3100,4936.3c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2960" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2995.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2995.457,4932.211z" />
    				<g id="cross-2960" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009.1,4935.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3041.4,4936.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2961" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2936.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2936.457,4932.211z" />
    				<g id="cross-2961" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.5,4935.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2981.8,4935.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2962" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2877.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2877.457,4932.211z" />
    				<g id="cross-2962" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2891.3,4935.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2923.6,4935.7
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2963" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2818.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2818.457,4932.211z" />
    				<g id="cross-2963" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2832,4935.1c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2864.3,4935.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2964" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2759.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2759.457,4932.211z" />
    				<g id="cross-2964" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.6,4934.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2804.9,4935.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2965" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2700.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2700.457,4932.211z" />
    				<g id="cross-2965" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2714,4934.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2746.3,4935.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2966" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2641.457,4932.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2641.457,4932.211z" />
    				<g id="cross-2966" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2654.2,4934.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2686.6,4934.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- C ROW 14 -->

    			<g id="seat-2967" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2308.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2308.457,4935.211z" />
    				<g id="cross-2967" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2323.2,4940.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2355.5,4940.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2968" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2249.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2249.457,4935.211z" />
    				<g id="cross-2968" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2264,4940.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2296.3,4940.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2969" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2190.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2190.457,4935.211z" />
    				<g id="cross-2969" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2205.2,4940.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2237.5,4940.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2970" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2131.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2131.457,4935.211z" />
    				<g id="cross-2970" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2146.2,4940c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2178.5,4940.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2971" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2072.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2072.457,4935.211z" />
    				<g id="cross-2971" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2087.2,4940.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2119.5,4941c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2972" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2013.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2013.457,4935.211z" />
    				<g id="cross-2972" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2028.2,4940.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2060.5,4941.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2973" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1954.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1954.457,4935.211z" />
    				<g id="cross-2973" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1969.2,4941c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2001.5,4941.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2974" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1895.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1895.457,4935.211z" />
    				<g id="cross-2974" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1910.2,4939.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1942.5,4940.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2975" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1837.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1837.457,4935.211z" />
    				<g id="cross-2975" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1851.2,4941.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1883.5,4941.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2976" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1778.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1778.457,4935.211z" />
    				<g id="cross-2976" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1792.2,4941.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1824.5,4941.7
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2977" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1719.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1719.457,4935.211z" />
    				<g id="cross-2977" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1732.9,4939.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1765.2,4940c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2978" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1660.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1660.457,4935.211z" />
    				<g id="cross-2978" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1674.2,4939.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1706.5,4939.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2979" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1601.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1601.457,4935.211z" />
    				<g id="cross-2979" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1614.7,4939.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1647,4939.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2980" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1542.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1542.457,4935.211z" />
    				<g id="cross-2980" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1556.5,4939.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1588.8,4939.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2981" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1483.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1483.457,4935.211z" />
    				<g id="cross-2981" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1497.1,4938.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1529.4,4939.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2982" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1424.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1424.457,4935.211z" />
    				<g id="cross-2982" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1437.7,4938.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1470,4939.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2983" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1365.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1365.457,4935.211z" />
    				<g id="cross-2983" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1379.2,4938.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1411.5,4938.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2984" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1306.457,4935.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1306.457,4935.211z" />
    				<g id="cross-2984" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1319.4,4938.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1351.7,4938.7
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- C ROW 15 -->

    			<g id="seat-2985" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3761.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3761.457,5062.211z" />
    				<g id="cross-2985" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3775.9,5066.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3808.2,5066.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2986" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3702.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3702.457,5062.211z" />
    				<g id="cross-2986" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3716.7,5066.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3749,5066.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2987" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3643.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3643.457,5062.211z" />
    				<g id="cross-2987" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3657.9,5066.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3690.2,5066.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2988" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3584.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3584.457,5062.211z" />
    				<g id="cross-2988" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3598.9,5066.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3631.2,5066.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2989" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3525.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3525.457,5062.211z" />
    				<g id="cross-2989" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3539.9,5066.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3572.2,5067c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2990" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3466.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3466.457,5062.211z" />
    				<g id="cross-2990" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3480.9,5066.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3513.2,5067.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2991" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3407.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3407.457,5062.211z" />
    				<g id="cross-2991" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M3421.9,5067c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3454.2,5067.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2992" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3348.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3348.457,5062.211z" />
    				<g id="cross-2992" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3362.9,5065.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3395.2,5066.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2993" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3290.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3290.457,5062.211z" />
    				<g id="cross-2993" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3303.9,5067.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3336.2,5067.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2994" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3231.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3231.457,5062.211z" />
    				<g id="cross-2994" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3244.9,5067.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3277.2,5067.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2995" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3172.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3172.457,5062.211z" />
    				<g id="cross-2995" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3185.6,5065.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3217.9,5066.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2996" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3113.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3113.457,5062.211z" />
    				<g id="cross-2996" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3126.9,5065.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3159.2,5065.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2997" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M3054.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L3054.457,5062.211z" />
    				<g id="cross-2997" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3067.4,5065.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3099.7,5065.7
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2998" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2995.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2995.457,5062.211z" />
    				<g id="cross-2998" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3009.2,5065.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M3041.5,5065.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-2999" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2936.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2936.457,5062.211z" />
    				<g id="cross-2999" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2949.8,5064.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2982.1,5065.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3000" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2877.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2877.457,5062.211z" />
    				<g id="cross-3000" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2890.4,5064.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2922.7,5065.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3001" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2818.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2818.457,5062.211z" />
    				<g id="cross-3001" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2831.9,5064.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2864.2,5064.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3002" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2759.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2759.457,5062.211z" />
    				<g id="cross-3002" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2772.1,5064.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2804.4,5064.7
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3003" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2700.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2700.457,5062.211z" />
    				<g id="cross-3003" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2714.2,5064.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2746.5,5065.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3004" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2641.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2641.457,5062.211z" />
    				<g id="cross-3004" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2654.1,5064.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2686.4,5064.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- C ROW 16 -->

    			<g id="seat-3005" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2308.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2308.457,5062.211z" />
    				<g id="cross-3005" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2322.2,5066.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2354.5,5066.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3006" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2249.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2249.457,5062.211z" />
    				<g id="cross-3006" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2263.1,5066.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2295.4,5066.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3007" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2190.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2190.457,5062.211z" />
    				<g id="cross-3007" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2204.2,5066.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2236.5,5066.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3008" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2131.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2131.457,5062.211z" />
    				<g id="cross-3008" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2145.2,5066.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2177.5,5066.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3009" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2072.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2072.457,5062.211z" />
    				<g id="cross-3009" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2086.2,5066.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M2118.5,5067c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3010" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M2013.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L2013.457,5062.211z" />
    				<g id="cross-3010" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2027.2,5066.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2059.5,5067.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3011" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1954.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1954.457,5062.211z" />
    				<g id="cross-3011" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1968.2,5067c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M2000.5,5067.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3012" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1895.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1895.457,5062.211z" />
    				<g id="cross-3012" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1909.2,5065.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1941.5,5066.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3013" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1837.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1837.457,5062.211z" />
    				<g id="cross-3013" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1850.2,5067.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1882.5,5067.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3014" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1778.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1778.457,5062.211z" />
    				<g id="cross-3014" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1791.2,5067.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1823.5,5067.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3015" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1719.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1719.457,5062.211z" />
    				<g id="cross-3015" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1731.9,5065.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1764.2,5066.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3016" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1660.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1660.457,5062.211z" />
    				<g id="cross-3016" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1673.3,5065.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1705.6,5065.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3017" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1601.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1601.457,5062.211z" />
    				<g id="cross-3017" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1613.7,5065.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1646,5065.7c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3018" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1542.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1542.457,5062.211z" />
    				<g id="cross-3018" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1555.5,5065.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1587.8,5065.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3019" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1483.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1483.457,5062.211z" />
    				<g id="cross-3019" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1496.2,5064.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1528.5,5065.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3020" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1424.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1424.457,5062.211z" />
    				<g id="cross-3020" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1436.8,5064.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1469.1,5065.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3021" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1365.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1365.457,5062.211z" />
    				<g id="cross-3021" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1378.2,5064.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1410.5,5064.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3022" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1306.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1306.457,5062.211z" />
    				<g id="cross-3022" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1318.4,5064.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1350.7,5064.7
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3023" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1247.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1247.457,5062.211z" />
    				<g id="cross-3023" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1260.6,5064.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1292.9,5065.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3024" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1188.457,5062.211
    				c-0.009-1.781-0.113-4.566,1.115-5.738c1.229-1.178,3.791-0.736,5.678-0.748l44.842-0.258c1.885-0.012,4.279-0.477,5.521,0.682
    				c1.243,1.16,1.332,3.943,1.343,5.727l0.198,34.379c-6.282,15.723-25.51,14.291-29.284,14.311l0,0
    				c-3.769,0.023-25.036,0.248-29.213-13.545L1188.457,5062.211z" />
    				<g id="cross-3024" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1200.4,5064.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1232.7,5064.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- SECTION D -->

    			<!-- D ROW 1 -->

    			<g id="seat-3025" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,4070.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,4070.557z" />
    				<g id="cross-3025" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1463.2,4083.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1495.5,4084.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3026" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,4011.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,4011.557z" />
    				<g id="cross-3026" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1463.4,4024.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1495.7,4025.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3027" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,3952.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,3952.557z" />
    				<g id="cross-3027" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1463,3965.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1495.3,3966.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3028" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,3893.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,3893.557z" />
    				<g id="cross-3028" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1461.5,3906.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1493.8,3907.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3029" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,3834.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,3834.557z" />
    				<g id="cross-3029" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1463.6,3847.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1495.9,3848.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3030" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,3775.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,3775.557z" />
    				<g id="cross-3030" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1461.3,3788.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1493.6,3789.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3031" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,3716.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,3716.557z" />
    				<g id="cross-3031" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1461.1,3729.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1493.4,3730.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3032" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,3657.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,3657.557z" />
    				<g id="cross-3032" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1463.8,3670.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1496.1,3671.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3033" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,3598.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,3598.557z" />
    				<g id="cross-3033" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1460.9,3611.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1493.2,3612.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3034" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1498.411,3539.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1498.411,3539.557z" />
    				<g id="cross-3034" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1461.5,3552.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1493.8,3553.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 2 -->

    			<g id="seat-3035" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,3210.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,3210.557z" />
    				<g id="cross-3035" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1463.9,3223.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1496.2,3224.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3036" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,3151.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,3151.557z" />
    				<g id="cross-3036" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1462.5,3164.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1494.8,3165.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3037" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,3092.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,3092.557z" />
    				<g id="cross-3037" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1464.1,3105.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1496.4,3106.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3038" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,3033.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,3033.557z" />
    				<g id="cross-3038" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1464.3,3046.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1496.6,3047.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3039" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,2974.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,2974.557z" />
    				<g id="cross-3039" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1464.5,2987.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1496.8,2988.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3040" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,2915.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,2915.557z" />
    				<g id="cross-3040" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1464.7,2928.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1497,2929.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3041" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,2856.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,2856.557z" />
    				<g id="cross-3041" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1464.9,2869.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1497.2,2870.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3042" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,2797.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,2797.557z" />
    				<g id="cross-3042" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1464.3,2810.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1496.6,2811.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3043" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,2738.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,2738.557z" />
    				<g id="cross-3043" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1462.7,2751.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1495,2752.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3044" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1499.411,2679.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1499.411,2679.557z" />
    				<g id="cross-3044" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1462.9,2692.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1495.2,2693.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 3 -->

    			<g id="seat-3045" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,4070.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,4070.557z" />
    				<g id="cross-3045" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1350.7,4083.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1383,4083.8c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3046" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,4011.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,4011.557z" />
    				<g id="cross-3046" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1349.3,4024.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1381.6,4024.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3047" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,3952.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,3952.557z" />
    				<g id="cross-3047" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1350.9,3965.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1383.2,3965.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3048" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,3893.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,3893.557z" />
    				<g id="cross-3048" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1351.1,3906.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1383.4,3906.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3049" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,3834.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,3834.557z" />
    				<g id="cross-3049" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1351.3,3847.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1383.6,3847.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3050" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,3775.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,3775.557z" />
    				<g id="cross-3050" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1351.5,3788.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1383.8,3788.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3051" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,3716.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,3716.557z" />
    				<g id="cross-3051" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1351.7,3729.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1384,3729.8c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3052" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,3657.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,3657.557z" />
    				<g id="cross-3052" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1351.1,3670.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1383.4,3670.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3053" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,3598.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,3598.557z" />
    				<g id="cross-3053" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1349.5,3611.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1381.8,3611.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3054" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1387.411,3539.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1387.411,3539.557z" />
    				<g id="cross-3054" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1349.7,3552.4c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1382,3552.8c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 4 -->

    			<g id="seat-3055" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,3210.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,3210.557z" />
    				<g id="cross-3055" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1346.7,3223.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1379,3224c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3056" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,3151.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,3151.557z" />
    				<g id="cross-3056" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1345.3,3164.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1377.6,3165c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3057" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,3092.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,3092.557z" />
    				<g id="cross-3057" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1346.9,3105.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1379.2,3106c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3058" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,3033.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,3033.557z" />
    				<g id="cross-3058" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1347.1,3046.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1379.4,3047c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3059" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,2974.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,2974.557z" />
    				<g id="cross-3059" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1347.3,2987.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1379.6,2988c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3060" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,2915.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,2915.557z" />
    				<g id="cross-3060" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1347.5,2928.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1379.8,2929c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3061" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,2856.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,2856.557z" />
    				<g id="cross-3061" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1347.7,2869.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1380,2870c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3062" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,2797.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,2797.557z" />
    				<g id="cross-3062" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1347.1,2810.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1379.4,2811c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3063" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,2738.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,2738.557z" />
    				<g id="cross-3063" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1345.5,2751.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1377.8,2752c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3064" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1383.411,2679.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1383.411,2679.557z" />
    				<g id="cross-3064" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1345.7,2692.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1378,2693c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 5 -->

    			<g id="seat-3065" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,4070.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,4070.557z" />
    				<g id="cross-3065" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1238.7,4083.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1271,4084c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3066" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,4011.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,4011.557z" />
    				<g id="cross-3066" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1237.3,4024.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1269.6,4025c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3067" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,3952.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,3952.557z" />
    				<g id="cross-3067" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1238.9,3965.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1271.2,3966c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3068" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,3893.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,3893.557z" />
    				<g id="cross-3068" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1239.1,3906.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1271.4,3907c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3069" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,3834.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,3834.557z" />
    				<g id="cross-3069" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1239.3,3847.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1271.6,3848c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3070" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,3775.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,3775.557z" />
    				<g id="cross-3070" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1239.5,3788.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1271.8,3789c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3071" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,3716.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,3716.557z" />
    				<g id="cross-3071" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1239.7,3729.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1272,3730c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3072" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,3657.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,3657.557z" />
    				<g id="cross-3072" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1239.1,3670.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1271.4,3671c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3073" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,3598.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,3598.557z" />
    				<g id="cross-3073" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1237.5,3611.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1269.8,3612c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3074" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1275.411,3539.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1275.411,3539.557z" />
    				<g id="cross-3074" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1237.7,3552.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1270,3553c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 6 -->

    			<g id="seat-3075" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,3210.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,3210.557z" />
    				<g id="cross-3075" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1235.7,3223.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1268,3224c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3076" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,3151.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,3151.557z" />
    				<g id="cross-3076" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1234.3,3164.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1266.6,3165c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3077" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,3092.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,3092.557z" />
    				<g id="cross-3077" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1235.9,3105.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1268.2,3106c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3078" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,3033.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,3033.557z" />
    				<g id="cross-3078" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1236.1,3046.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1268.4,3047c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3079" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,2974.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,2974.557z" />
    				<g id="cross-3079" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1236.3,2987.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1268.6,2988c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3080" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,2915.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,2915.557z" />
    				<g id="cross-3080" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1236.5,2928.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1268.8,2929c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3081" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,2856.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,2856.557z" />
    				<g id="cross-3081" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1236.7,2869.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1269,2870c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3082" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,2797.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,2797.557z" />
    				<g id="cross-3082" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1236.1,2810.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1268.4,2811c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3083" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,2738.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,2738.557z" />
    				<g id="cross-3083" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1234.5,2751.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1266.8,2752c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3084" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1272.411,2679.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1272.411,2679.557z" />
    				<g id="cross-3084" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1234.7,2692.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1267,2693c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 7 -->

    			<g id="seat-3085" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,4188.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,4188.557z" />
    				<g id="cross-3085" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1125.7,4201.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1158,4202c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3086" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,4129.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,4129.557z" />
    				<g id="cross-3086" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1124.3,4142.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1156.6,4143c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3087" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,4070.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,4070.557z" />
    				<g id="cross-3087" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1125.9,4083.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1158.2,4084c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3088" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,4011.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,4011.557z" />
    				<g id="cross-3088" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1126.1,4024.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1158.4,4025c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3089" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,3952.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,3952.557z" />
    				<g id="cross-3089">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1126.3,3965.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1158.6,3966c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3090" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,3893.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,3893.557z" />
    				<g id="cross-3090" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1126.5,3906.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1158.8,3907c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3091" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,3834.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,3834.557z" />
    				<g id="cross-3091" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1126.7,3847.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1159,3848c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3092" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,3775.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,3775.557z" />
    				<g id="cross-3092" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1126.1,3788.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1158.4,3789c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3093" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,3716.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,3716.557z" />
    				<g id="cross-3093" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1124.5,3729.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1156.8,3730c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3094" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,3657.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,3657.557z" />
    				<g id="cross-3094" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1124.7,3670.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1157,3671c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3095" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,3598.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,3598.557z" />
    				<g id="cross-3095" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1124.3,3611.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1156.6,3612.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3096" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1162.411,3539.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1162.411,3539.557z" />
    				<g id="cross-3096" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1124.1,3552.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1156.4,3552.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 8 -->

    			<g id="seat-3097" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,3210.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,3210.557z" />
    				<g id="cross-3097" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1118.8,3223.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1151.1,3223.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3098" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,3151.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,3151.557z" />
    				<g id="cross-3098" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1117.4,3164.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1149.7,3164.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3099" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,3092.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,3092.557z" />
    				<g id="cross-3099" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1119,3105.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1151.3,3105.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3100" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,3033.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,3033.557z" />
    				<g id="cross-3100" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1119.2,3046.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1151.5,3046.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3101" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,2974.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,2974.557z" />
    				<g id="cross-3101" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1119.4,2987.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1151.7,2987.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3102" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,2915.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,2915.557z" />
    				<g id="cross-3102" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1119.6,2928.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1151.9,2928.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3103" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,2856.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,2856.557z" />
    				<g id="cross-3103" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1119.8,2869.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1152.1,2869.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3104" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,2797.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,2797.557z" />
    				<g id="cross-3104" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1119.2,2810.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1151.5,2810.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3105" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,2738.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,2738.557z" />
    				<g id="cross-3105" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1117.6,2751.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1149.9,2751.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3106" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,2679.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,2679.557z" />
    				<g id="cross-3106" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1117.8,2692.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1150.1,2692.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3107" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,2620.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,2620.557z" />
    				<g id="cross-3107" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1117.4,2633.6c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1149.7,2633.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3108" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1155.411,2561.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1155.411,2561.557z" />
    				<g id="cross-3108" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1117.2,2573.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1149.5,2574.2
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 9 -->

    			<g id="seat-3109" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,4306.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,4306.557z" />
    				<g id="cross-3109" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1015.8,4320.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1048.1,4320.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3110" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,4247.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,4247.557z" />
    				<g id="cross-3110" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1014.3,4261.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1046.6,4261.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3111" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,4188.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,4188.557z" />
    				<g id="cross-3111" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1015.9,4202.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1048.2,4202.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3112" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,4129.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,4129.557z" />
    				<g id="cross-3112" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1016.1,4143.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1048.4,4143.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3113" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,4070.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,4070.557z" />
    				<g id="cross-3113" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1016.3,4084.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1048.6,4084.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3114" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,4011.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,4011.557z" />
    				<g id="cross-3114" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1016.5,4025.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1048.8,4025.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3115" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,3952.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,3952.557z" />
    				<g id="cross-3115" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1016.7,3966.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1049,3966.5c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3116" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,3893.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,3893.557z" />
    				<g id="cross-3116" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1016.1,3907.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1048.4,3907.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3117" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,3834.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,3834.557z" />
    				<g id="cross-3117" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1014.5,3848.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1046.8,3848.5
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3118" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,3775.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,3775.557z" />
    				<g id="cross-3118" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1014.7,3789.1c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1047,3789.5c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3119" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,3716.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,3716.557z" />
    				<g id="cross-3119" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1014.3,3730.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1046.6,3730.8
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3120" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,3657.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,3657.557z" />
    				<g id="cross-3120" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1014.1,3670.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1046.4,3671.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3121" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,3598.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,3598.557z" />
    				<g id="cross-3121" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1013.9,3611.2c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1046.2,3611.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3122" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1051.411,3539.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1051.411,3539.557z" />
    				<g id="cross-3122" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1014.9,3552.9c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1047.2,3553.3
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 10 -->

    			<g id="seat-3123" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,3210.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,3210.557z" />
    				<g id="cross-3123" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1010.9,3223.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1043.2,3224.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3124" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,3151.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,3151.557z" />
    				<g id="cross-3124" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1009.5,3164.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1041.8,3165.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3125" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,3092.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,3092.557z" />
    				<g id="cross-3125" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1011.1,3105.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1043.4,3106.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3126" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,3033.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,3033.557z" />
    				<g id="cross-3126" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1011.3,3046.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1043.6,3047.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3127" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2974.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2974.557z" />
    				<g id="cross-3127" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1011.5,2987.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1043.8,2988.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3128" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2915.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2915.557z" />
    				<g id="cross-3128" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1011.7,2928.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1044,2929.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3129" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2856.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2856.557z" />
    				<g id="cross-3129" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1011.9,2869.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1044.2,2870.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3130" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2797.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2797.557z" />
    				<g id="cross-3130" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1011.3,2810.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1043.6,2811.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3131" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2738.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2738.557z" />
    				<g id="cross-3131" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1009.7,2751.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1042,2752.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3132" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2679.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2679.557z" />
    				<g id="cross-3132" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1009.9,2692.7c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1042.2,2693.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3133" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2620.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2620.557z" />
    				<g id="cross-3133" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M1009.5,2634c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1041.8,2634.4
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3134" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2561.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2561.557z" />
    				<g id="cross-3134" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1009.3,2574.3c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1041.6,2574.6
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3135" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2502.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2502.557z" />
    				<g id="cross-3135" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1009.1,2514.8c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1041.4,2515.1
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3136" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M1047.411,2443.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L1047.411,2443.557z" />
    				<g id="cross-3136" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1010.1,2456.5c13.9,13.9,31.9,31.9,31.9,31.9
    					" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M1042.4,2456.9
    					c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>

    			<!-- D ROW 11 -->

    			<g id="seat-3137" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,4424.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,4424.557z" />
    				<g id="cross-3137" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M893.9,4437.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M926.2,4438.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3138" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,4365.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,4365.557z" />
    				<g id="cross-3138" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M892.5,4378.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M924.8,4379.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3139" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,4306.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,4306.557z" />
    				<g id="cross-3139" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.1,4319.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M926.4,4320.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3140" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,4247.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,4247.557z" />
    				<g id="cross-3140" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.3,4260.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M926.6,4261.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3141" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,4188.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,4188.557z" />
    				<g id="cross-3141" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.5,4201.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M926.8,4202.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3142" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,4129.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,4129.557z" />
    				<g id="cross-3142" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.7,4142.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M927,4143.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3143" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,4070.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,4070.557z" />
    				<g id="cross-3143" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.9,4083.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M927.2,4084.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3144" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,4011.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,4011.557z" />
    				<g id="cross-3144" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.3,4024.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M926.6,4025.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3145" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,3952.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,3952.557z" />
    				<g id="cross-3145" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M892.7,3965.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M925,3966.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3146" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,3893.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,3893.557z" />
    				<g id="cross-3146" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M892.9,3906.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M925.2,3907.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3147" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,3834.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,3834.557z" />
    				<g id="cross-3147" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M892.5,3848c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M924.8,3848.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3148" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,3775.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,3775.557z" />
    				<g id="cross-3148" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M892.3,3788.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M924.6,3788.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3149" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,3716.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,3716.557z" />
    				<g id="cross-3149" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M892.1,3728.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M924.4,3729.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3150" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,3657.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,3657.557z" />
    				<g id="cross-3150" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M893.1,3670.5c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M925.4,3670.9c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3151" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,3598.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,3598.557z" />
    				<g id="cross-3151" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M892.7,3611.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M925,3612.3c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3152" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M930.411,3539.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L930.411,3539.557z" />
    				<g id="cross-3152" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M891.9,3553.1c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M924.2,3553.5c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>

    			<!-- D ROW 12 -->

    			<g id="seat-3153" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,3210.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,3210.557z" />
    				<g id="cross-3153" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M896.2,3223.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M928.5,3223.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3154" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,3151.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,3151.557z" />
    				<g id="cross-3154" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.7,3164.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M927,3164.8c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3155" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,3092.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,3092.557z" />
    				<g id="cross-3155" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M896.4,3105.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M928.7,3105.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3156" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,3033.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,3033.557z" />
    				<g id="cross-3156" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M896.6,3046.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M928.9,3046.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3157" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2974.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2974.557z" />
    				<g id="cross-3157" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M896.8,2987.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M929.1,2987.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3158" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2915.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2915.557z" />
    				<g id="cross-3158" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M896.9,2928.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M929.2,2928.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3159" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2856.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2856.557z" />
    				<g id="cross-3159" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M897.1,2869.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M929.4,2869.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3160" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2797.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2797.557z" />
    				<g id="cross-3160" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M896.6,2810.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M928.9,2810.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3161" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2738.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2738.557z" />
    				<g id="cross-3161" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.9,2751.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M927.2,2751.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3162" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2679.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2679.557z" />
    				<g id="cross-3162" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M895.1,2692.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M927.4,2692.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3163" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2620.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2620.557z" />
    				<g id="cross-3163" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.7,2633.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M927,2634.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3164" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2561.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2561.557z" />
    				<g id="cross-3164" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.5,2574c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M926.8,2574.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3165" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2502.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2502.557z" />
    				<g id="cross-3165" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.3,2514.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M926.6,2514.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3166" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2443.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2443.557z" />
    				<g id="cross-3166" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M895.3,2456.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M927.6,2456.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3167" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2384.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2384.557z" />
    				<g id="cross-3167" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.9,2397.6c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M927.2,2398c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3168" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M931.411,2325.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L931.411,2325.557z" />
    				<g id="cross-3168" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M894.1,2338.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M926.5,2339.2c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>

    			<!-- D ROW 13 -->

    			<g id="seat-3169" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4542.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4542.557z" />
    				<g id="cross-3169" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M791.9,4555.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M824.2,4556.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3170" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4483.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4483.557z" />
    				<g id="cross-3170" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M790.4,4496.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M822.8,4497.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3171" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4424.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4424.557z" />
    				<g id="cross-3171" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M792.1,4437.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M824.4,4438.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3172" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4365.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4365.557z" />
    				<g id="cross-3172" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M792.3,4378.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M824.6,4379.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3173" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4306.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4306.557z" />
    				<g id="cross-3173" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M792.5,4319.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M824.8,4320.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3174" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4247.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4247.557z" />
    				<g id="cross-3174" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M792.7,4260.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M825,4261.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3175" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4188.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4188.557z" />
    				<g id="cross-3175" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M792.9,4201.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M825.2,4202.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3176" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4129.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4129.557z" />
    				<g id="cross-3176" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M792.3,4142.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M824.6,4143.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3177" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4070.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4070.557z" />
    				<g id="cross-3177" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M790.6,4083.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M822.9,4084.1C809,4098,791,4116,791,4116" />
    				</g>
    			</g>
    			<g id="seat-3178" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,4011.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,4011.557z" />
    				<g id="cross-3178" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M790.8,4024.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M823.1,4025.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3179" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,3952.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,3952.557z" />
    				<g id="cross-3179" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M790.4,3966c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M822.8,3966.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3180" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,3893.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,3893.557z" />
    				<g id="cross-3180" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M790.3,3906.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M822.6,3906.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3181" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,3834.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,3834.557z" />
    				<g id="cross-3181" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M790.1,3846.7c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M822.4,3847.1c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3182" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,3775.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,3775.557z" />
    				<g id="cross-3182" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M791,3788.5c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M823.3,3788.9c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3183" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,3716.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,3716.557z" />
    				<g id="cross-3183" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M790.6,3729.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M822.9,3730.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3184" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,3657.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,3657.557z" />
    				<g id="cross-3184" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M789.9,3671.1c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M822.2,3671.5c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3185" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,3598.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,3598.557z" />
    				<g id="cross-3185" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M789.5,3611c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M821.8,3611.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3186" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M826.411,3539.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L826.411,3539.557z" />
    				<g id="cross-3186" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M789.3,3552c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M821.6,3552.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>

    			<!-- D ROW 14 -->

    			<g id="seat-3187" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,3210.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,3210.557z" />
    				<g id="cross-3187" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M788.7,3223.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M821,3224.3c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3188" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,3151.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,3151.557z" />
    				<g id="cross-3188" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M787.3,3164.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M819.6,3165.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3189" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,3092.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,3092.557z" />
    				<g id="cross-3189" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M788.9,3105.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M821.2,3106.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3190" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,3033.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,3033.557z" />
    				<g id="cross-3190" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M789.1,3046.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M821.4,3047.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3191" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2974.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2974.557z" />
    				<g id="cross-3191" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M789.3,2987.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M821.6,2988.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3192" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2915.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2915.557z" />
    				<g id="cross-3192" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M789.5,2928.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M821.8,2929.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3193" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2856.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2856.557z" />
    				<g id="cross-3193" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M789.7,2869.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M822,2870.3c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3194" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2797.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2797.557z" />
    				<g id="cross-3194" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M789.1,2810.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M821.4,2811.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3195" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2738.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2738.557z" />
    				<g id="cross-3195" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M787.4,2751.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M819.8,2752.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3196" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2679.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2679.557z" />
    				<g id="cross-3196" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M787.6,2692.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M819.9,2693.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3197" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2620.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2620.557z" />
    				<g id="cross-3197" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M787.3,2634.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M819.6,2634.7c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3198" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2561.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2561.557z" />
    				<g id="cross-3198" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M787.1,2574.5c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M819.4,2574.9c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3199" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2502.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2502.557z" />
    				<g id="cross-3199" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M786.9,2515c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M819.2,2515.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3200" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2443.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2443.557z" />
    				<g id="cross-3200" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M787.8,2456.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M820.1,2457.2c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3201" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2384.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2384.557z" />
    				<g id="cross-3201" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M787.4,2398.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M819.8,2398.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3202" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2325.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2325.557z" />
    				<g id="cross-3202" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M786.7,2339.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M819,2339.8c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3203" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2266.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2266.557z" />
    				<g id="cross-3203" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M786.3,2279.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M818.6,2279.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3204" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M823.411,2207.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L823.411,2207.557z" />
    				<g id="cross-3204" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M786.1,2220.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M818.4,2220.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>

    			<!-- D ROW 15 -->

    			<g id="seat-3205" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4660.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4660.557z" />
    				<g id="cross-3205" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.3,4673.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M690.6,4674.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3206" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4601.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4601.557z" />
    				<g id="cross-3206" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.9,4614.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.2,4615.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3207" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4542.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4542.557z" />
    				<g id="cross-3207" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.5,4555.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M690.8,4556.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3208" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4483.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4483.557z" />
    				<g id="cross-3208" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.7,4496.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M691,4497.3c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3209" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4424.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4424.557z" />
    				<g id="cross-3209" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.9,4437.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M691.2,4438.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3210" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4365.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4365.557z" />
    				<g id="cross-3210" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M659.1,4378.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M691.4,4379.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3211" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4306.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4306.557z" />
    				<g id="cross-3211" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M659.3,4319.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M691.6,4320.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3212" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4247.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4247.557z" />
    				<g id="cross-3212" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.7,4260.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M691,4261.3c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3213" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4188.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4188.557z" />
    				<g id="cross-3213" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.1,4201.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.4,4202.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3214" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4129.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4129.557z" />
    				<g id="cross-3214" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.2,4142.9c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.5,4143.3c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3215" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4070.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4070.557z" />
    				<g id="cross-3215" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.9,4084.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.2,4084.7c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3216" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,4011.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,4011.557z" />
    				<g id="cross-3216" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.7,4024.5c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M689,4024.9c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3217" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3952.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3952.557z" />
    				<g id="cross-3217" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.5,3965c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M688.8,3965.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3218" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3893.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3893.557z" />
    				<g id="cross-3218" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.4,3906.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.7,3907.2c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3219" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3834.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3834.557z" />
    				<g id="cross-3219" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.1,3848.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.4,3848.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3220" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3775.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3775.557z" />
    				<g id="cross-3220" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.3,3789.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M688.6,3789.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3221" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3716.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3716.557z" />
    				<g id="cross-3221" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M655.9,3729.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M688.2,3729.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3222" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3657.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3657.557z" />
    				<g id="cross-3222" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M655.7,3670.3c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M688,3670.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3223" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3598.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3598.557z" />
    				<g id="cross-3223" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.5,3610.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M688.8,3611.2c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3224" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3539.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3539.557z" />
    				<g id="cross-3224" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.6,3551.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.9,3552.2c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>

    			<!-- D ROW 16 -->

    			<g id="seat-3225" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3210.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3210.557z" />
    				<g id="cross-3225" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.3,3224.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M690.6,3224.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3226" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3151.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3151.557z" />
    				<g id="cross-3226" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.9,3165.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.2,3165.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3227" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3092.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3092.557z" />
    				<g id="cross-3227" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.5,3106.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M690.8,3106.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3228" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,3033.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,3033.557z" />
    				<g id="cross-3228" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.7,3047.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M691,3047.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3229" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2974.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2974.557z" />
    				<g id="cross-3229" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.9,2988.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M691.2,2988.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3230" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2915.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2915.557z" />
    				<g id="cross-3230" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M659.1,2929.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M691.4,2929.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3231" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2856.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2856.557z" />
    				<g id="cross-3231" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M659.3,2870.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M691.6,2870.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3232" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2797.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2797.557z" />
    				<g id="cross-3232" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M658.7,2811.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M691,2811.6c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3233" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2738.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2738.557z" />
    				<g id="cross-3233" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.1,2752.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.4,2752.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3234" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2679.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2679.557z" />
    				<g id="cross-3234" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.2,2693.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.5,2693.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3235" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2620.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2620.557z" />
    				<g id="cross-3235" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.9,2634.5c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.2,2634.9c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3236" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2561.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2561.557z" />
    				<g id="cross-3236" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.7,2574.8c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M689,2575.1c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3237" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2502.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2502.557z" />
    				<g id="cross-3237" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.5,2515.2c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M688.8,2515.6c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3238" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2443.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2443.557z" />
    				<g id="cross-3238" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.4,2457c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.7,2457.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3239" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2384.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2384.557z" />
    				<g id="cross-3239" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.1,2398.4c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.4,2398.8c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3240" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2325.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2325.557z" />
    				<g id="cross-3240" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.3,2339.6c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M688.6,2340c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3241" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2266.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2266.557z" />
    				<g id="cross-3241" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M655.9,2279.5c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M688.2,2279.9c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3242" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2207.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2207.557z" />
    				<g id="cross-3242" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M655.7,2220.5c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M688,2220.9c-13.9,13.9-31.9,31.9-31.9,31.9" />
    				</g>
    			</g>
    			<g id="seat-3243" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2148.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2148.557z" />
    				<g id="cross-3243" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M656.5,2161c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M688.8,2161.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    			<g id="seat-3244" class="booth">
    				<path class="booth-fill" fill="#FFFFFF" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M694.411,2089.557
    				c1.78-0.009,4.566-0.113,5.738,1.115c1.177,1.229,0.736,3.791,0.748,5.678l0.257,44.842c0.012,1.885,0.478,4.279-0.681,5.521
    				c-1.161,1.243-3.944,1.332-5.728,1.343l-34.379,0.198c-15.722-6.282-14.29-25.51-14.311-29.284l0,0
    				c-0.022-3.769-0.247-25.036,13.546-29.213L694.411,2089.557z" />
    				<g id="cross-3244" class="cross">
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10"
    						d="M657.6,2102c13.9,13.9,31.9,31.9,31.9,31.9" />
    					<path class="cross-line" fill="#FFFFFF" stroke="#000000" stroke-width="4" stroke-miterlimit="10" d="M689.9,2102.4c-13.9,13.9-31.9,31.9-31.9,31.9
    					" />
    				</g>
    			</g>
    		</g>
    	</svg>

    	<!-- The pivot -->
    	<svg id="svg-scrim" class="svg svg-scrim">
    		<circle id="pivot" class="pivot" cx="0" cy="0" r="6" fill="none" />
    	</svg>
    </div>

    <!-- The Reset Button and Instructions -->
    <div class="controls">
    	<div id="info" class="info">
    	<ul>
    		<li><strong>Click and drag</strong> inside the window to pan the seat map. <strong>Scroll</strong> to zoom; <strong>use the + and - buttons</strong> if scrolling doesn't work for you.</li>
    		<li><strong>Double-click</strong> a seat to select/unselect. <strong>Tap it once</strong> to select/unselect on mobile.</li>
    		<li><strong>White Seats</strong> - available.</li>
    		<li><mark>Yellow Seats</mark> - requested.</li>
    		<li><strong style="color:grey;">Grey Seats</strong> - taken.</li>
    	</ul>
    	</div>

    	<button id="reset" class="mdl-button mdl-js-button mdl-button--raised mdl-js-ripple-effect controls-button">
    	Reset
    	</button>

    </div>

  <!-- JAVASCRIPT - TippyJS plugin -->
  <script src="https://polyfill.io/v3/polyfill.min.js?features=Array.prototype.find,Promise,Object.assign"></script>
  <script src="https://unpkg.com/@popperjs/core@2/dist/umd/popper.min.js"></script>
  <script src="https://unpkg.com/tippy.js@6/dist/tippy-bundle.umd.js"></script>
  <script src="https://unpkg.com/@popperjs/core@2"></script>
  <script src="https://unpkg.com/tippy.js@6"></script>

  <script>
    console.clear();
    
    let svg = document.querySelector("#svg");
    let reset = document.querySelector("#reset");
    let pivot = document.querySelector("#pivot");
    let proxy = document.createElement("div");
    let viewport = document.querySelector("#viewport");
    let container = document.querySelector('#container');

    // Zoom Button controls
    let zoomIn = document.getElementById("zoomIn");
    let zoomOut = document.getElementById("zoomOut");

    let rotateThreshold = 4;
    let reachedThreshold = false;

    // The arrays below should be populated by the IDs of booths that are not available to the user seeking to reserve the booth.
    // takenSeats (unavailable by default) - GREY
    // pendingSeats (not approved yet, but reserved) - YELLOW
    let takenSeats = ["seat-2340", "seat-2888", "seat-2777"];
    let pendingSeats = ["seat-2555"];

    $(document).ready(function(){
        $.each(takenSeats, function(index, value){
            $("#" + value).find('path.booth-fill').addClass("grey");
        });
        
        $.each(pendingSeats, function(index, value){
            $("#" + value).find('path.booth-fill').addClass("yellow");
			$("#" + value).find('path.cross-line').addClass("cross-line-yellow");
        });
        
        // Tooltips must be created inside this function as well, or will not work
        tippy('.booth-fill.yellow', {
            content: 'Reservation pending...'
        });
        
    });
    
    // Changing the cursor to pointer on hover over booths
    $('g.booth').hover(function() {
        if ($(this).find('path.booth-fill') && !$(this).find('path.booth-fill').hasClass("yellow") && !$(this).find('path.booth-fill').hasClass("grey")){
            $(this).css('cursor', 'pointer');
			$(this).find('path.cross-line').toggleClass("cross-line-grey");
			$(this).find('path.booth-fill').toggleClass("booth-fill-grey");
        }
    });
    
    // Toggling double-clicked paths GREEN (for PC only)
    let booth_cart = []; 

    $('g.booth').on("dblclick", function() {
        if ($(this).find('path.booth-fill').hasClass("green")) {
            $(this).find('path.booth-fill').removeClass("green");
			$(this).find('path.cross-line').removeClass("cross-line-green");
            booth_cart.splice( $.inArray(this.id, booth_cart), 1);
            displayIds()  
        } else {
            if (!$(this).find('path.booth-fill').hasClass("red") && !$(this).find('path.booth-fill').hasClass("yellow") && !$(this).find('path.booth-fill').hasClass("grey")){
            $(this).find('path.booth-fill').addClass("green");
			$(this).find('path.cross-line').addClass("cross-line-green");
            booth_cart.push(this.id);
            displayIds()
            }
        }
    });

    // This function handles the booth selection for MOBILE DEVICES / TAPPING
    $(function(){
        $('g.booth').bind("tap", function(){
            if ($(this).find('path.booth-fill').hasClass("green")) {
            $(this).find('path.booth-fill').removeClass("green");
			$(this).find('path.cross-line').removeClass("cross-line-green");
            booth_cart.splice( $.inArray(this.id, booth_cart), 1);
            displayIds()  
        } else {
            if (!$(this).find('path.booth-fill').hasClass("red") && !$(this).find('path.booth-fill').hasClass("yellow") && !$(this).find('path.booth-fill').hasClass("grey")){
            $(this).find('path.booth-fill').addClass("green");
			$(this).find('path.cross-line').addClass("cross-line-green");
            booth_cart.push(this.id);
            displayIds()
            }
        }
        });
    });

    // This function displays the booth IDs at the top of the screen
    function displayIds() {
      document.getElementById("booth-cart").innerHTML = booth_cart;
    }

    // Mobile Pinch Zoom - Hammer.js
    function hammerzoom(elem) {
        hammertime = new Hammer(elem, {});
        hammertime.get('pinch').set({
            enable: true
        });

        var posX = 0,
            posY = 0,
            scale = 1,
            last_scale = 1,
            last_posX = 0,
            last_posY = 0,
            max_pos_x = 0,
            max_pos_y = 0,
            transform = "",
            el = elem;

        hammertime.on('pinch pinchend', function(ev) {
            
            //pinch
            if (ev.type == "pinch") {
                scale = Math.max(.999, Math.min(last_scale * (ev.scale), 30)); 
            }
            if(ev.type == "pinchend"){last_scale = scale;}

            if (scale != 1) {
                transform =
                    "translate3d(" + posX + "px," + posY + "px, 0) " +
                    "scale3d(" + scale + ", " + scale + ", 1)";
            }

            if (transform) {
                el.style.webkitTransform = transform;
            }
        });
    }

    hammerzoom(svg);

    // Panning and Zooming functionality for PC
    let point = svg.createSVGPoint();
    let startClient = svg.createSVGPoint();
    let startGlobal = svg.createSVGPoint();

    // Creating a View Box for the svg with id #svg
    let viewBox = svg.viewBox.baseVal;

    let cachedViewBox = {
    x: viewBox.x,
    y: viewBox.y,
    width: viewBox.width,
    height: viewBox.height
    };

    // Zooming    
    let zoom = {
    animation: new TimelineLite(),
    scaleFactor: 1.6,
    duration: 0.5,
    ease: Power2.easeOut,
    };

    // Zooming functions for the BUTTONS
    function limits(){
        let tS=this.target._gsTransform.scaleX , mx=10 , mn=1;
        let testX = this.target;
        if(tS<mn||tS>mx){
            TweenLite.set(this.target,{scale:tS>mx?mx:mn});
        };
    };

    zoomIn.onclick = function() {
        TweenLite.to(viewport, 0.5, {scale:"+=0.5",onUpdate:limits}); 
    };

    zoomOut.onclick = function() {
        TweenLite.to(viewport, 0.5, {scale:"-=0.5",onUpdate:limits}); 
    };
    // END Zooming functions for the buttons ---------

    // TweenLite is a GSAP animation tool 
    TweenLite.set(pivot, { scale: 0 });

    // Pivot animation - pivoting and resetting
    let resetAnimation = new TimelineLite();
    let pivotAnimation = TweenLite.to(pivot, 0.1, {
    alpha: 1,
    scale: 1,
    paused: true,
    });

    // Panning Animation 
    let pannable = new Draggable(proxy, {
    throwResistance: 3000,
    trigger: svg,
    throwProps: false, 
    onPress: selectDraggable,
    onDrag: updateViewBox,
    onThrowUpdate: updateViewBox,
    allowContextMenu: true,
    });

    // Reset Button event listener
    reset.addEventListener("click", resetViewport);

    container.addEventListener("wheel", onWheel, {passive: false});

    window.addEventListener("resize", function() {
        pivotAnimation.reverse();
    });

    //
    // ON WHEEL
    // =========================================================================== 
    function onWheel(event) {
        event.preventDefault();
        

        pivotAnimation.reverse();
        
        let normalized;  
        let delta = event.wheelDelta;

        if (delta) {
            normalized = (delta % 120) == 0 ? delta / 120 : delta / 12;
        } else {
            delta = event.deltaY || event.detail || 0;
            normalized = -(delta % 3 ? delta * 10 : delta / 3);
        }
        
        let scaleDelta = normalized > 0 ? 1 / zoom.scaleFactor : zoom.scaleFactor;
        
        point.x = event.clientX;
        point.y = event.clientY;
        
        let startPoint = point.matrixTransform(svg.getScreenCTM().inverse());
            
        let fromVars = {
            ease: zoom.ease,
            x: viewBox.x,
            y: viewBox.y,
            width: viewBox.width,
            height: viewBox.height,
        };
        
        viewBox.x -= (startPoint.x - viewBox.x) * (scaleDelta - 1);
        viewBox.y -= (startPoint.y - viewBox.y) * (scaleDelta - 1);
        viewBox.width *= scaleDelta;
        viewBox.height *= scaleDelta;
            
        zoom.animation = TweenLite.from(viewBox, zoom.duration, fromVars);  
    }

    //
    // SELECT DRAGGABLE
    // Smooth draggable/panning animation goes here 
    // =========================================================================== 
    function selectDraggable(event) {
    
    if (resetAnimation.isActive()) {
        resetAnimation.kill();
    }
        
    startClient.x = this.pointerX;
    startClient.y = this.pointerY;
    startGlobal = startClient.matrixTransform(svg.getScreenCTM().inverse());
    
    // Don't disable this entire function, as the panning will become wonky

    TweenLite.set(proxy, { 
        
        x: this.pointerX, 
        y: this.pointerY
        });
        
    pannable.enable().update().startDrag(event);
    pivotAnimation.reverse();
    }

    //
    // RESET VIEWPORT
    // The viewport Reset and Update sections allow you to view the image
    // =========================================================================== 
    function resetViewport() {
        
    let duration = 0.8;
    let ease = Power3.easeOut;
    
    pivotAnimation.reverse();
    
    if (pannable.tween) {
        pannable.tween.kill();
    }
        
    resetAnimation.clear()
        .to(viewBox, duration, {
        x: cachedViewBox.x,
        y: cachedViewBox.y,
        width: cachedViewBox.width,
        height: cachedViewBox.height,
        ease: ease
        }, 0)
        .to(viewport, duration, {
        attr: { transform: "matrix(1,0,0,1,0,0)" },
        smoothOrigin: false,
        svgOrigin: "0 0",
        ease: ease
        }, 0)
    }

    //
    // UPDATE VIEWBOX
    // =========================================================================== 
    function updateViewBox() {
    
    if (zoom.animation.isActive()) {
        return;
    }
    
    point.x = this.x;
    point.y = this.y;
    
    let moveGlobal = point.matrixTransform(svg.getScreenCTM().inverse());
        
    viewBox.x -= (moveGlobal.x - startGlobal.x);
    viewBox.y -= (moveGlobal.y - startGlobal.y); 
    }

  </script>
</body>
</html>
