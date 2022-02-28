# new-Vega_Garcia
import app from "./app";
import './database'


app.listen(3000);

console.log("oyendo en el puerto", 3000)

{
    "name": "plataforma",
    "version": "1.0.0",
    "description": "Taller Plataforma",
    "main": "index.js",
    "scripts": {
        "build": "babel src --out-dir build",
        "babel-node": "babel-node --presets=@babel/preset-env",
        "dev": "nodemon --exec npm run babel-node src/index.js",
        "start": "node build/index.js"
    },
    "keywords": [],
    "author": "Abel Vega",
    "docente": "Guillermo Pizarro",
    "license": "ISC",
    "dependencies": {
        "bcryptjs": "^2.4.3",
        "cors": "^2.8.5",
        "dotenv": "^16.0.0",
        "express": "^4.17.3",
        "helmet": "^5.0.2",
        "jsonwebtoken": "^8.5.1",
        "mongoose": "^6.2.3",
        "morgan": "^1.10.0"
    },
    "devDependencies": {
        "@babel/cli": "^7.17.6",
        "@babel/core": "^7.17.5",
        "@babel/node": "^7.16.8",
        "@babel/preset-env": "^7.16.11",
        "nodemon": "^2.0.15"
    }
}



import mongoose from "mongoose";

mongoose.connect("mongodb://Localhost/companydb", {
    userNewUrlParser: true,
    useUnifiedTopology: true,
})
.then(db => console.log( 'Db is connected'))
.catch(error => console.log(error))


"use strict";

var _express = _interopRequireDefault(require("express"));

function _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { "default": obj }; }

var app = (0, _express["default"])();
app.listen(3000);
console.log("oyendo en el puerto", 3000);


import {Schema, model } from'mongoose'

new Schem({
    name: String,
    category: String,
    price: Number,
    imgURL: String,
}, {
    timestamps: true,
    versionKey: false
})

export default model('Product', productSchema);


import express from 'express'
import morgan from 'morgan';
import pkg from '../package.json'
const app = express()

import productsRoutes from './routes/products.routes'

app.set('pkg', pkg)

app.use(morgan('dev'));
app.get('/', (req, res) => {
    res.json({
        autor: app.get('pkg').author,
        descripcion: app.get('pkg').description,
        docente: app.get('pkg').docente,
        version: app.get('pkg').version,
    })
})

app.use('/products', productsRoutes)

export default app;



import {Router} from 'express'
const router = Router()

export default router;


import {Router} from 'express'
const router = Router()

import * as productsCtrl from '../controllers/products.controller'

router.post('/', productsCtrl.getProduct)
router.get('/', productsCtrl.getProduct)
router.get('/:productId', productsCtrl.getProductById)
router.put('/:productId', productsCtrl.updateProductById)
router.delate('/:productId', productsCtrl.deleteProductById)


export default router;



import {Product} from'../models/Product'

export const createProduct = (req, res) => {
    res.json('creating product')

}  

export const getProduct = (req, res) => {
    res.json("get products")
}


export const getProductById = (req, res) => {
    
}


export const updateProductById = (req, res) => {
    
}


export const deleteProductById = (req, res) => {
    
}



import {Router} from 'express'
const router = Router()

export default router;



{
    "presets":[
        "@babel/preset-env"
    ]
}
